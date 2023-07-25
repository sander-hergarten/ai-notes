The main object of this book will be the behaviour of large sets of discrete random variables. A discrete random variable $X$ is completely defined by the set of values it can take, $\mathcal X$, which we assume to be a finite set, and its probability distribution $\set{p_X(x)}_{x\in\mathcal X}$. The value $p_X(x)$ is the probability that the random variable $X$ takes the value $x$. The probability distribution $p_X:\mathcal X\rightarrow[0,1]$ must satisfy the normalization condition
$$\sum_{x\in \mathcal X}p_X(x)=1$$ We shall denote $\mathbb P(A)$ the probability of an event $A\subset \mathcal X$, so that $p_X(x)=\mathbb P(X=x)$. 

If $f(X)$ is a real valued function of the random variable $X$, the expectation value of $f(x)$, which we shall also call the average of $f$, is devoted by:
$$\mathbb E f=\sum_{x\in\mathcal X}p_X(x)f(x)$$
