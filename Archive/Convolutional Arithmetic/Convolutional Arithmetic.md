---
tags:
- programming/machine-learning/computer-vision
---
$i$ : input dimension
$k$ : kernel size
$s$ : stride length
$p$ : padding size
$o$ : output dimension 
## Zero Padding, Unit Stride:
For any $i$ and $k$ and for $s=1$ and $p=0$,
$$o=(i-k)+1$$
## No Zero Padding, Unit Stride
For any $i$, $k$ and $p$ and for $s=1$ 
$$o=(i-k)+2p+1$$
#### Half (same) padding
Having the output size be the same as the input size (i.e., $o = i$) can be a desirable property:

For any $i$ and for $k$ odd ($k = 2n+1$, $n \in \mathbb{N}$), $s=1$ and $p=\lfloor k/2\rfloor=n$,
$$\begin{align} 
o =& \quad i+ 2\lfloor k/2 \rfloor- (k-1)\\
 =& \quad i+2n-2n \\
 =& \quad i
\end{align}$$
#### Full Padding
Using proper padding the kernel increases the output size with respect to the input size.

For any $i$ and $k$, and for $p=k−1$ and $s=1$,
$$\begin{align}
o =& \quad i+2(k-1)-(k-1)\\
=& \quad i+(k-1)
\end{align}$$
This is sometimes referred to as full padding, because in this setting every possible partial or complete superimposition of the kernel on the input feature map is taken into account.

## No Zero Padding, Non Unit Stride
For any $i$ , $k$ and $s$, and for $p=0$
$$o=\left \lfloor\frac{i-k}{s} \right \rfloor +1$$
# Zero Padding, Non Unit Stride
The most general case

For any $i$ , $k$, $p$ and $s$
$$
o=\left\lfloor \frac{i+2p-k}{s} \right\rfloor+1
$$
# Pooling Arithmetic
In a neural network, pooling layers provide invariance to small translations of the input. The most common kind of pooling is max pooling, which consists in splitting the input in (usually non-overlapping) patches and outputting the maximum value of each patch. Other kinds of pooling exist, e.g., mean or average pooling, which all share the same idea of aggregating the input locally by applying a non-linearity to the content of some patches

For any $i$, $k$ and $s$
$$o=\left \lfloor\frac{i-k}{s} \right \rfloor +1$$

