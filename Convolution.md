(https://www.statlect.com/glossary/convolutions)
In probability theory, a convolution is a mathematical operation that allows us to derive the distribution of a sum of two random variables from the distributions of the two summands. 

In the case of discrete random variables, the convolution is obtained by summing a series of products of the [[Probability Mass Function (PMF)]]

in the case of continuous random variables it is obtained by integrating the product of their [[Probability Density Function]]

# Convolution of PMF 
Let $x$ be a discrete random variable with support $R_X$ and PMF $p_X(x)$.

Let $Y$ be another discrete random variable, independent of $X$, with support $R_y$ and PMF $p_Y(y)$

The PMF $p_Z(z)$ of the sum $Z=X+Y$ can be derived using one of the following two formulae:
$$\begin{align} 
p_Z(z)=\sum_{y\in R_Y}p_X(z-y)p_Y(Y)\\
p_Z(z)=\sum_{x\in R_X}p_Y(z-x)p_X(x)
\end{align}$$
# Convolution of PDF
If $X$ and $Y$ are continuous, independent, and have probability density functions $f_X(x)$ and $f_Y(y)$ respectively, the convolution formulae become:
$$\begin{align}
f_Z(z)=\int_{-\infty}^{\infty} f_X(z-y)f_Y(y)dy \\
f_Z(z)=\int_{-\infty}^{\infty} f_Y(z-x)f_X(x)dx
\end{align}$$
