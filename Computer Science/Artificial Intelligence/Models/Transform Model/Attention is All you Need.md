Understaing of [[Google - Attention is All you need.pdf]]

# Introduction

[[Recurrent Neural Networks]], [[Long Short-Term Memory]] [^12] and [[Gated Recurrent Neural Networks]] [^7] in particular, have been firmly established as state of the art approaches in sequence modeling and transduction problems such as language modeling and machine translation. [^29][^2][^5] Numerous efforts have since continued to push the boundaries of [[Recurrent Neural Network Language Models]] and [[Encoder-Decoder Architecture]]. [^31][^21][^13]

[[Recurrent Neural Networks]] typically factor computation along the symbol positions of the input and output sequences. 

Aligning the positions to steps in computation time, they generate a sequence of hidden states $h_t$, as a function of the previous hidden state $h_{t - 1}$ and the input for position $t$. This inherently sequential nature precludes parallelization within training examples, which becomes critical at longer sequence lengths, as memory constraints limit batching across examples. 

> [!note] Thought
> So, because the execution of an input depends on the previous input, it is impossible to parallelize the execution, because to execute $input_t$ with $h_t$ it is needed to get $h_{t-1}$ on the $input_{t-1}$ exection 

Recent work has achieved significant improvements in computational efficiency through factorization tricks [^18] and conditional computation [^26], while also improving model performance in case of the latter. 

The fundamental constraint of [[Sequential Computation]], however, remains. Attention mechanisms have become an integral part of compelling sequence modeling and transduction models in various tasks, allowing modeling of dependencies without regard to their distance in the input or output sequences [^2][^16]. In all but a few cases [^22], however, such attention mechanisms are used in conjunction with a recurrent network. 

> [!note] Thought 
> [[Recurrent Neural Networks]] have [[Sequential Computation]] obligatory, so it is impossible to parallalize it. 


In this work we propose the [[Transformer Model]], a model architecture eschewing (avoiding) recurrence and instead relying entirely on an [[Attention Mechanism]] to draw global dependencies between input and output. The Transformer allows for significantly more parallelization and can reach a new state of the art in translation quality after being trained for as little as twelve hours on eight [[P100 GPU]]s.

> [!question]
> What is an [[Attention Mechanism]]?

# Background

The goal of reducing [[Sequential Computation]] also forms the foundation of the [[Extended Neural GPU]] [^20], [[ByteNet]] [^15] and [[Convolutional Sequence to Sequence Learning|ConvS2S]] [^8], all of which use [[Convolutional Neural Network]] as basic building block, computing hidden representations in parallel for all input and output positions. 

In these models, the number of operations required to relate signals from two arbitrary input or output positions grows in the distance between positions, linearly for [[Convolutional Sequence to Sequence Learning|ConvS2S]] and logarithmically for [[ByteNet]]. 

This makes it more difficult to learn dependencies between distant positions [^11]. 

>[!note] Thought
>So, when this [[Convolutional Neural Network]] models tries to relate distant inputs/outputs, it increase computation cost.

In the Transformer this is reduced to a constant number of operations, albeit at the cost of reduced effective resolution due to averaging attention-weighted positions, an effect we counteract with Multi-Head Attention as described in section 3.2. 

[[Self-Attention Mechanism|Self-Attention]], sometimes called intra-attention is an [[Attention Mechanism]] relating different positions of a single sequence in order to compute a representation of the sequence. 

[[Self-Attention Mechanism|Self-Attention]] has been used successfully in a variety of tasks including reading comprehension, abstractive summarization, textual entailment and learning task-independent sentence representations [^4][^22][^23][^19].  ^de7133

[[End-to-End Memory Network]] are based on a recurrent attention mechanism instead of sequence aligned recurrence and have been shown to perform well on simple-language question answering and language modeling tasks [^28].  ^574ee2

>[!important]
> To the best of our knowledge, however, the Transformer is the first transduction model relying entirely on self-attention to compute representations of its input and output without using sequence aligned [[Recurrent Neural Networks|RNNs]] or [[Convolutional Neural Network|convolution]]. 

In the following sections, we will describe the Transformer, motivate self-attention and discuss its advantages over models such as [^14][^15] and [^8].

# Model Architecture

Most competitive neural sequence transduction models have an [[Encoder-Decoder Architecture|encoder-decoder structure]] [^5][^2][^29].

Here, the encoder maps an input sequence of symbol representations $(x_1 , \dots, x_n )$ to a sequence of continuous representations $z = (z_1 , ..., z_n)$. 

Given $z$, the decoder then generates an output
sequence $(y_1 , \dots, y_m)$ of symbols one element at a time. 

At each step the model is auto-regressive [^9], consuming the previously generated symbols as additional input when generating the next.

The Transformer follows this overall architecture using stacked [[Self-Attention Mechanism|Self Attention]] and point-wise, [[Fully Connected Layer|Fully Connected Layers]] for both the [[Encoder]] and [[Decoder]], shown in the left and right halves of Figure 1, respectively.


>[!question] 
>Stacked [[Self-Attention Mechanism]]?
>Point-wise?

>[!note] Thought
>So, in resume, the [[Transformer Model]] is similar to a [[Encoder-Decoder Architecture]]

##### **3.1 Encoder and Decoder Stacks**
##### **3.1.1 Encoder**
The encoder is composed of a stack of $N = 6$ identical layers. 

Each layer has two sub-layers. 

The first is a multi-head self-attention mechanism, and the second is a simple, position-wise fully connected feed-forward network. 

We employ a residual connection [^10] around each of the two sub-layers, followed by layer normalization [^1]. 

That is, the output of each sub-layer is $\text{LayerNorm}(x + \text{Sublayer}(x))$, where $\text{Sublayer}(x)$ is the function implemented by the sub-layer itself. 

To facilitate these residual connections, all sub-layers in the model, as well as the embedding layers, produce outputs of dimension $d_\text{model} = 512$.

>[!question]
>- What is Residual Connections?
>- What is Normalization Layer?
>- What is Position-wise?
>- What is Feed-forward network?
>- What is Embedding Layers?

##### **3.1.2 Decoder**
The decoder is also composed of a stack of $N = 6$ identical layers. 

In addition to the two sub-layers in each encoder layer, the decoder inserts a third sub-layer, which performs multi-head attention over the output of the encoder stack.

Similar to the encoder, we employ residual connections around each of the sub-layers, followed by layer normalization. 

We also modify the self-attention sub-layer in the decoder stack to prevent positions from attending to subsequent positions. 

This masking, combined with fact that the output embeddings are offset by one position, ensures that the predictions for position $i$ can depend only on the known outputs at positions less than $i$.

**The Transformer - Model Architecture**
![[Pasted image 20240613215908.png]]

##### **3.2 Attention**

An attention function can be described as mapping a query and a set of key-value pairs to an output, where the query, keys, values, and output are all vectors. The output is computed as a weighted sum of the values, where the weight assigned to each value is computed by a compatibility function of the query with the corresponding key.

##### **3.2.1 Scaled Dot-Product Attention**

![[Pasted image 20240613224921.png]]

We call our particular attention "Scaled Dot-Product Attention" . 

The input consists of queries and keys of dimension $d_k$ , and values of dimension $d_v$ . 

We compute the dot products of the query with all keys, divide each by $sqrt{d_k}$ , and apply a [[Softmax Function]] to obtain the weights on the In practice, we compute the [[attention function]] on a set of queries simultaneously, packed together into a matrix $Q$. 

The keys and values are also packed together into matrices $K$ and $V$.

We compute the matrix of outputs as:

$$\text{Attention}(Q,K,V) = \text{softmax}(\frac{QK^T}{\sqrt{d_k}})V$$

The two most commonly used attention functions are [[Additive Attention]] [^2], and [[Dot-Product Attention|dot-product (multiplicative) attention]].

[[Dot-Product Attention]] is identical to our algorithm, except for the scaling factor of $\frac{1}{\sqrt{d_k}}$. 

[[Additive Attention]] computes the compatibility function using a [[Feed-Forward Network]] with a single hidden layer. 

While the two are similar in theoretical complexity, [[Dot-Product Attention]] is much faster and more space-efficient in practice, since it can be implemented using highly optimized matrix multiplication code.

While for small values of $d_k$ the two mechanisms perform similarly, [[Additive Attention]] outperforms [[Dot-Product Attention]] without scaling for larger values of $d_k$ [^3]. 

We suspect that for large values of $d_k$ , the dot products grow large in magnitude, pushing the [[Softmax Function]] into regions where it has extremely small gradients [^4]. 

To counteract this effect, we scale the dot products by $\frac{1}{\sqrt{d_k}}$.

##### 3.2.2 Multi-Head Attention

Instead of performing a single attention function with $d_\text{model}-\text{dimensional keys}$, values and queries, we found it beneficial to linearly project the queries, keys and values $h$ times with different, learned linear projections to $d_k$ , $d_k$ and $d_v$ dimensions, respectively.

On each of these projected versions of queries, keys and values we then perform the attention function in parallel, yielding $d_v-\text{dimensional output values}$ .

These are concatenated and once again projected, resulting in the final values, as
depicted in Figure 2.

[[Multi-Head Attention]] allows the model to jointly attend to information from different representation subspaces at different positions.

With a single attention head, averaging inhibits this.

$$\text{MultiHead}(Q,K,V) = \text{Concat}(\text{head}_1, \dots, \text{head}_h)W^O$$
$$\text{where }\text{head}_i = \text{Attention}(QW_i^Q, KW_i^K, VW_i^V)$$

Where the projections are parameter matrices $W_i^Q \in \mathbb{R}^{d_\text{model} \times d_k}, W_i^K \in \mathbb{R}^{d_\text{model} \times d_k}, W_i^V \in \mathbb{R}^{d_\text{model} \times d_v} \text{ and } W^O \in \mathbb{R}^{hd_v \times d_\text{model}}$ .

In this work we employ $h = 8$ parallel attention layers, or heads.

For each of these we use $d_k = d_v = d_\text{model}/h = 64$. Due to the reduced dimension of each head. the total computational cost similar to that of single-head attention with full dimensionality.

# References

[^1]: Jimmy Lei Ba, Jamie Ryan Kiros, and Geoffrey E Hinton. Layer normalization. arXiv preprint arXiv:1607.06450, 2016. 

[^2]: Dzmitry Bahdanau, Kyunghyun Cho, and Yoshua Bengio. Neural machine translation by jointly learning to align and translate. CoRR, abs/1409.0473, 2014. 

[^3]: Denny Britz, Anna Goldie, Minh-Thang Luong, and Quoc V. Le. Massive exploration of neural machine translation architectures. CoRR, abs/1703.03906, 2017. 

[^4]: Jianpeng Cheng, Li Dong, and Mirella Lapata. Long short-term memory-networks for machine reading. arXiv preprint arXiv:1601.06733, 2016. 

[^5]: Kyunghyun Cho, Bart van Merrienboer, Caglar Gulcehre, Fethi Bougares, Holger Schwenk, and Yoshua Bengio. Learning phrase representations using rnn encoder-decoder for statistical machine translation. CoRR, abs/1406.1078, 2014. 

[^6]: Francois Chollet. Xception: Deep learning with depthwise separable convolutions. arXiv preprint arXiv:1610.02357, 2016. 

[^7]: Junyoung Chung, Çaglar Gülçehre, Kyunghyun Cho, and Yoshua Bengio. Empirical evaluation of gated recurrent neural networks on sequence modeling. CoRR, abs/1412.3555, 2014. 

[^8]: Jonas Gehring, Michael Auli, David Grangier, Denis Yarats, and Yann N. Dauphin. Convolutional sequence to sequence learning. arXiv preprint arXiv:1705.03122v2, 2017. 

[^9]: Alex Graves. Generating sequences with recurrent neural networks. arXiv preprint arXiv:1308.0850, 2013. 

[^10]: Kaiming He, Xiangyu Zhang, Shaoqing Ren, and Jian Sun. Deep residual learning for image recognition. In Proceedings of the IEEE Conference on Computer Vision and Pattern Recognition, pages 770–778, 2016. 

[^11]: Sepp Hochreiter, Yoshua Bengio, Paolo Frasconi, and Jürgen Schmidhuber. Gradient flow in recurrent nets: the difficulty of learning long-term dependencies, 2001. 

[^12]: Sepp Hochreiter and Jürgen Schmidhuber. Long short-term memory. Neural computation, 9(8):1735–1780, 1997. 

[^13]: Rafal Jozefowicz, Oriol Vinyals, Mike Schuster, Noam Shazeer, and Yonghui Wu. Exploring the limits of language modeling. arXiv preprint arXiv:1602.02410, 2016. 

[^14]: Łukasz Kaiser and Ilya Sutskever. Neural GPUs learn algorithms. In International Conference on Learning Representations (ICLR), 2016. 

[^15]: Nal Kalchbrenner, Lasse Espeholt, Karen Simonyan, Aaron van den Oord, Alex Graves, and Koray Kavukcuoglu. Neural machine translation in linear time. arXiv preprint arXiv:1610.10099v2, 2017. 

[^16]: Yoon Kim, Carl Denton, Luong Hoang, and Alexander M. Rush. Structured attention networks. In International Conference on Learning Representations, 2017. 

[^17]: Diederik Kingma and Jimmy Ba. Adam: A method for stochastic optimization. In ICLR, 2015. 

[^18]: Oleksii Kuchaiev and Boris Ginsburg. Factorization tricks for LSTM networks. arXiv preprint arXiv:1703.10722, 2017. 

[^19]: Zhouhan Lin, Minwei Feng, Cicero Nogueira dos Santos, Mo Yu, Bing Xiang, Bowen Zhou, and Yoshua Bengio. A structured self-attentive sentence embedding. arXiv preprint arXiv:1703.03130, 2017. 

[^20]: Samy Bengio Łukasz Kaiser. Can active memory replace attention? In Advances in Neural Information Processing Systems, (NIPS), 2016.

[^21]: Minh-Thang Luong, Hieu Pham, and Christopher D Manning. Effective approaches to attentionbased neural machine translation. arXiv preprint arXiv:1508.04025, 2015. 

[^22]: Ankur Parikh, Oscar Täckström, Dipanjan Das, and Jakob Uszkoreit. A decomposable attention model. In Empirical Methods in Natural Language Processing, 2016. 

[^23]: Romain Paulus, Caiming Xiong, and Richard Socher. A deep reinforced model for abstractive summarization. arXiv preprint arXiv:1705.04304, 2017. 

[^24]: Ofir Press and Lior Wolf. Using the output embedding to improve language models. arXiv preprint arXiv:1608.05859, 2016. 

[^25]: Rico Sennrich, Barry Haddow, and Alexandra Birch. Neural machine translation of rare words with subword units. arXiv preprint arXiv:1508.07909, 2015. 

[^26]: Noam Shazeer, Azalia Mirhoseini, Krzysztof Maziarz, Andy Davis, Quoc Le, Geoffrey Hinton, and Jeff Dean. Outrageously large neural networks: The sparsely-gated mixture-of-experts layer. arXiv preprint arXiv:1701.06538, 2017. 

[^27]: Nitish Srivastava, Geoffrey E Hinton, Alex Krizhevsky, Ilya Sutskever, and Ruslan Salakhutdinov. Dropout: a simple way to prevent neural networks from overfitting. Journal of Machine Learning Research, 15(1):1929–1958, 2014. 

[^28]: Sainbayar Sukhbaatar, arthur szlam, Jason Weston, and Rob Fergus. End-to-end memory networks. In C. Cortes, N. D. Lawrence, D. D. Lee, M. Sugiyama, and R. Garnett, editors, Advances in Neural Information Processing Systems 28, pages 2440–2448. Curran Associates, Inc., 2015. 

[^29]: Ilya Sutskever, Oriol Vinyals, and Quoc VV Le. Sequence to sequence learning with neural networks. In Advances in Neural Information Processing Systems, pages 3104–3112, 2014. 

[^30]: Christian Szegedy, Vincent Vanhoucke, Sergey Ioffe, Jonathon Shlens, and Zbigniew Wojna. Rethinking the inception architecture for computer vision. CoRR, abs/1512.00567, 2015. 

[^31]: Yonghui Wu, Mike Schuster, Zhifeng Chen, Quoc V Le, Mohammad Norouzi, Wolfgang Macherey, Maxim Krikun, Yuan Cao, Qin Gao, Klaus Macherey, et al. Google’s neural machine translation system: Bridging the gap between human and machine translation. arXiv preprint arXiv:1609.08144, 2016. 

[^32]: Jie Zhou, Ying Cao, Xuguang Wang, Peng Li, and Wei Xu. Deep recurrent models with fast-forward connections for neural machine translation. CoRR, abs/1606.04199, 2016.
