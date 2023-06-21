(https://www.probabilitycourse.com/chapter4/4_2_2_exponential.php)

The exponential distribution is one of the widely used continuous distributions. It is often used to model the time elapsed between events.

A continuous random variable $X$ s said to have an exponential distribution with parameters $\lambda > 0$, shown as $X\sim Exponential(\lambda)$ if its [[Probability Density Function]] is given by: $$f_X(x)=\begin{cases}\lambda e^{-\lambda x}&\quad x>0 \\ 0&\quad otherwise \end{cases}$$![[Pasted image 20230602223524.png]]
It is convenient to use the unit step function defined as:
$$u(x)=\begin{cases}1&\quad x\ge 0\\0&\quad otherwise\end{cases}$$
so we can write the PDF of an $Exponential(\lambda)$ random variable as: $$f_X(x)=\lambda e^{-\lambda x}u(x)$$
To find the [[Cumulative Distribution Function]], mean and variance. For $x>0$, we have:$$F_X(x)=\int_{0}^{x}\lambda e^{-\lambda t} dt=1-e^{-\lambda x}$$
so the CDF is:
$$F_X(x)=\left(1-e^{-\lambda x}\right)u(x)$$
let $X\sim Exponential(\lambda)$ we can find its expected value as follows, using integration by parts:
$$mean =\frac{1}{\lambda}$$
$$var=\frac{2}{\lambda^2}$$
# Intuition
you are waiting for the next customer to enter a store. In each millisecond the probability that a new customer enters the store is very small. As such you can imagine a coin being flipped every millisecond and if it lands on heads a new customer enters. This follows and exponential distribution.

The exponential distribution is memoryless. That means that if no new customer came until time $a$, the distribution of waiting time from time $a$ until the next customer is the same when you started at time zero.