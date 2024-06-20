
Is a [[Neural Network]]

**Personal Thoughts**
- It seems that Recurrent Models can't use Parallelism...


title: Cited in [[Attention is All you Need]]

Typically factor computation along the symbol positions of the input and output sequences. 

Aligning the positions to steps in computation time, they generate a sequence of hidden states $h_t$, as a function of the previous hidden state $h_{t - 1}$ and the input for position $t$. 

This inherently sequential nature precludes parallelization within training examples, which becomes critical at longer sequence lengths, as memory constraints limit batching across examples.


title: Cited in [Wiki - Recurrent Neural Network](https://en.wikipedia.org/wiki/Recurrent_neural_network)


A **recurrent neural network** (**RNN**) is one of the two broad types of [artificial neural network](https://en.wikipedia.org/wiki/Artificial_neural_network "Artificial neural network"), characterized by direction of the flow of information between its layers. In contrast to the uni-directional [feedforward neural network](https://en.wikipedia.org/wiki/Feedforward_neural_network "Feedforward neural network"), it is a bi-directional artificial neural network, meaning that it allows the output from some nodes to affect subsequent input to the same nodes. Their ability to use internal state (memory) to process arbitrary sequences of inputs[[1]](https://en.wikipedia.org/wiki/Recurrent_neural_network#cite_note-1)[[2]](https://en.wikipedia.org/wiki/Recurrent_neural_network#cite_note-2)[[3]](https://en.wikipedia.org/wiki/Recurrent_neural_network#cite_note-3) makes them applicable to tasks such as unsegmented, connected [handwriting recognition](https://en.wikipedia.org/wiki/Handwriting_recognition "Handwriting recognition")[[4]](https://en.wikipedia.org/wiki/Recurrent_neural_network#cite_note-4) or [speech recognition](https://en.wikipedia.org/wiki/Speech_recognition "Speech recognition").[[5]](https://en.wikipedia.org/wiki/Recurrent_neural_network#cite_note-sak2014-5)[[6]](https://en.wikipedia.org/wiki/Recurrent_neural_network#cite_note-liwu2015-6) The term "recurrent neural network" is used to refer to the class of networks with an [infinite impulse response](https://en.wikipedia.org/wiki/Infinite_impulse_response "Infinite impulse response"), whereas "[convolutional neural network](https://en.wikipedia.org/wiki/Convolutional_neural_network "Convolutional neural network")" refers to the class of [finite impulse](https://en.wikipedia.org/wiki/Finite_impulse_response "Finite impulse response") response. Both classes of networks exhibit temporal [dynamic behavior](https://en.wikipedia.org/wiki/Dynamic_system "Dynamic system").[[7]](https://en.wikipedia.org/wiki/Recurrent_neural_network#cite_note-7) A finite impulse recurrent network is a [directed acyclic graph](https://en.wikipedia.org/wiki/Directed_acyclic_graph "Directed acyclic graph") that can be unrolled and replaced with a strictly feedforward neural network, while an infinite impulse recurrent network is a [directed cyclic graph](https://en.wikipedia.org/wiki/Directed_cyclic_graph "Directed cyclic graph") that cannot be unrolled.

Additional stored states and the storage under direct control by the network can be added to both [infinite-impulse](https://en.wikipedia.org/wiki/Infinite_impulse_response "Infinite impulse response") and [finite-impulse](https://en.wikipedia.org/wiki/Finite_impulse_response "Finite impulse response") networks. Another network or graph can also replace the storage if that incorporates time delays or has feedback loops. Such controlled states are referred to as gated states or gated memory and are part of [long short-term memory](https://en.wikipedia.org/wiki/Long_short-term_memory "Long short-term memory") networks (LSTMs) and [gated recurrent units](https://en.wikipedia.org/wiki/Gated_recurrent_unit "Gated recurrent unit"). This is also called Feedback Neural Network (FNN). Recurrent neural networks are theoretically [Turing complete](https://en.wikipedia.org/wiki/Turing_complete "Turing complete") and can run arbitrary programs to process arbitrary sequences of inputs.[[8]](https://en.wikipedia.org/wiki/Recurrent_neural_network#cite_note-8)

```
