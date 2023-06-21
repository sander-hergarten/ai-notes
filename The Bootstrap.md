The bootstrap is a nonparametric method for estimating standard errors from our point prediction and computing confidence intervals. 

Let 
$$T_n=g(X_1,...,X_n)$$
be a statistic, that is, any function of the data. Suppose we want to know $\mathbb V_F(T_n)$, the variance of $T_n$ (i.e. standard error). We have written  $\mathbb V_F$ since the variance is dependent on the unknown distribution function $F$. 

The bootstrap idea has two parts:
1. Estimate the variance $V_F(T_n)$ with the variance of the [[Estimating thew CDF and Statistical Functionals#The Empirical Distribution Function|empirical distribution function]] to get $V_{\hat{F}_n}(T_n)$
2. In more complicated cases the EDF is not easy to calculate. This leads us to approximate $V_{\hat{F}_n}(T_n)$ using simulation

# Simulation
Suppose we draw an IID sample $Y_1,...,Y_B$ from a distribution $G$. By the law of large numbers,
$$\overline{Y}_n=\frac{1}{B}\sum^B_{j=1}Y_j\xrightarrow{P}\int y dG(y)=\mathbb E(Y)$$
as $B\rightarrow \infty$. This can be changed up to calculate the variance $\mathbb V(Y)$
$$\frac{1}{B}\sum^B_{j=1}(Y_j-\overline{Y})^2$$
