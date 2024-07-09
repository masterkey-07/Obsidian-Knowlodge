The **softmax function,** also known as **softargmax** or **normalized exponential function**,  converts a vector of K real numbers into a [[Probability Distribution]] of K possible outcomes.

It is a generalization of the [[Logistic Function]] to multiple dimensions, and used in multinomial logistic regression. The softmax function is often used as the last activation function of a [[Neural Network]] to normalize the output of a network to a [[Probability Distribution]] over predicted output classes.

# Definition

The softmax function takes as input a vector $z$ of $K$ real numbers, and normalizes it into a [[Probability Distribution]] consisting of $K$ probabilities proportional to the exponentials of the input numbers. That is, prior to applying softmax, some vector components could be negative, or greater than one; and might not sum to 1; but after applying softmax, each component will be in the interval ${\displaystyle (0,1)}$, and the components will add up to 1, so that they can be interpreted as probabilities. Furthermore, the larger input components will correspond to larger probabilities.

Formally, the standard (unit) softmax function  $\sigma:\mathbb{R}^K \to (0,1)^K$, where ${\displaystyle K\geq 1}$, takes a vector ${\displaystyle \mathbf {z} =(z*{1},\dotsc ,z*{K})\in \mathbb {R} ^{K}}$ and computes each component of vector ${\displaystyle \sigma (\mathbf {z} )\in (0,1)^{K}}$ with

$$\sigma(z)_i = \frac{e^{z_i}}{\sum^K_{j=1}e^{z_j}}$$

In words, the softmax applies the standard exponential function to each element 𝑧𝑖!{\displaystyle z\_{i}} of the input vector 𝑧!{\displaystyle \mathbf {z} } (consisting of 𝐾!{\displaystyle K} real numbers), and normalizes these values by dividing by the sum of all these exponentials. The normalization ensures that the sum of the components of the output vector 𝜎(𝑧)!{\displaystyle \sigma (\mathbf {z} )} is 1. The term "softmax" derives from the amplifying effects of the exponential on any maxima in the input vector. For example, the standard softmax of (1,2,8)!{\displaystyle (1,2,8)} is approximately (0.001,0.002,0.997)!{\displaystyle (0.001,0.002,0.997)}, which amounts to assigning almost all of the total unit weight in the result to the position of the vector's maximal element (of 8).

In general, instead of e a different base "Base (exponentiation)") b > 0 can be used. As above, if b > 1 then larger input components will result in larger output probabilities, and increasing the value of b will create probability distributions that are more concentrated around the positions of the largest input values. Conversely, if 0 < b < 1 then smaller input components will result in larger output probabilities, and decreasing the value of b will create probability distributions that are more concentrated around the positions of the smallest input values. Writing 𝑏=𝑒𝛽!{\displaystyle b=e^{\beta }} or 𝑏=𝑒−𝛽!{\displaystyle b=e^{-\beta }}[a] (for real β)[b] yields the expressions:[c]

𝜎(𝑧)𝑖=𝑒𝛽𝑧𝑖∑𝑗=1𝐾𝑒𝛽𝑧𝑗 or 𝜎(𝑧)𝑖=𝑒−𝛽𝑧𝑖∑𝑗=1𝐾𝑒−𝛽𝑧𝑗 for 𝑖=1,…,𝐾.

!{\displaystyle \sigma (\mathbf {z} )_{i}={\frac {e^{\beta z_{i}}}{\sum _{j=1}^{K}e^{\beta z_{j}}}}{\text{ or }}\sigma (\mathbf {z} )_{i}={\frac {e^{-\beta z_{i}}}{\sum _{j=1}^{K}e^{-\beta z_{j}}}}{\text{ for }}i=1,\dotsc ,K.}

A value proportional to the reciprocal of β is sometimes referred to as the *temperature*: 𝛽=1/𝑘𝑇!{\textstyle \beta =1/kT}, where k is typically 1 or the Boltzmann constant and T is the temperature. A higher temperature results in a more uniform output distribution (i.e. with higher entropy; it is "more random"), while a lower temperature results in a sharper output distribution, with one value dominating.

In some fields, the base is fixed, corresponding to a fixed scale,[d] while in others the parameter β (or T) is varied.