The bootstrap is a [[Models, Statistical Inference and Learning#Parametric and Nonparametric Models|nonparametric method]] for estimating standard errors from our point prediction and computing confidence intervals. 

Let 
$$T_n=g(X_1,...,X_n)$$
be a statistic, that is, any function of the data. Suppose we want to know $\mathbb V_F(T_n)$, the variance of $T_n$ (i.e. standard error). We have written  $\mathbb V_F$ since the variance is dependent on the unknown distribution function $F$. 

The bootstrap idea has two parts:
1. Estimate the variance $V_F(T_n)$ with the variance of the [[Estimating thew CDF and Statistical Functionals#The Empirical Distribution Function|empirical distribution function]] to get $V_{\hat{F}_n}(T_n)$
2. In more complicated cases the EDF is not easy to calculate. This leads us to approximate $V_{\hat{F}_n}(T_n)$ using simulation

# Simulation
Suppose we draw an IID sample $Y_1,...,Y_B$ from a distribution $G$. By the [[Convergence of Random Variables#The Law of Large Numbers|law of large numbers]], 
$$\overline{Y}_n=\frac{1}{B}\sum^B_{j=1}Y_j\xrightarrow{P}\int y dG(y)=\mathbb E(Y)$$
as $B\rightarrow \infty$. This can be changed up to calculate the [[Moment#Variance|variance]] $\mathbb V(Y)$
$$\frac{1}{B}\sum^B_{j=1}(Y_j-\overline{Y})^2=\frac{1}{B}\sum^B_{j=1}Y_j^2-\left(\frac{1}{B}\sum^B_{j=1}Y_j\right)^2\xrightarrow{P}\int y^2dF(y)-\left(\int ydF(y)\right)^2=\mathbb V(Y)$$
as such we can use the sample variance of the simulated values to approximate the variance of $Y$

# Bootstrap Variance Estimation
Using simulation we can approximate $V_{\hat{F}_n}(T_n)$.  $\mathbb V_{\hat{F}_n}(T_n)$ means the variance of $T_n$ if the distribution of the data is $\hat{F}_n$. How can we simulate from the distribution of $T_n$ when the data are assumed to have distribution $\hat{F}_n$? We simulate $X_1^*,...,X_n^*$ from the EDF $\hat{F}_n$ and then compute a new $T^*_n =g(X_1^*,...,X_n^*)$. This constitutes one draw from the distribution of $T_n$. The idea is illustrated below:
![[Pasted image 20230621164956.png]]
To simulate $X_1^*,...,X_n^*$ from $\hat{F}_n$ we must look at the definition of the EDF. Since we put mass $\frac{1}{n}$ at each data point $X_1,...,X_n$ drawing an observation from this distribution is equivalent to drawing one point at random from the original data set. Thus, to simulate $X_1^*,...,X_n^*\sim \hat{F}_n$ it suffices to draw $n$ observations with replacement (one sample can be pulled twice) from the original dataset $X_1,...,X_n$ 

To sumerize
> [!example] Bootstrap Variance Estimation
> 1. Draw $X_1^*,...,X_n^*\sim \hat{F}_n$ 
> 2. Compute $X_1^*,...,X_n^*\sim \hat{F}_n$
> 3. Repeat steps 1 and 2, $B$ times, to get $T^*_{n,1}, ..., T^*_{n,B}$
> 4. Let $$v_{\text{boot}}=\frac{1}{B}\sum^B_{b=1}\left(T^*_{n,b}-\frac{1}{B}\sum^B_{r=1}T^*_{n,b}\right)^2 $$ 

# Bootstrap Confidence Intervals
There are several ways to construct bootstrap intervals:

## Normal Interval
The simplest is the Normal interval
$$T_n \pm z_{a/2}\hat{\text{se}}_{boot}$$
where $\hat{\text{se}}_{boot}$ is the bootstrap estimate of the standard error. This interval is not accurate unless the distribution of $T_n$ is close to normal.

## Pivotal Intervals
Let $\theta=T(F)$ and $\hat{\theta}_n=T(\hat{F}_n)$ and define the pivot $R_n=\hat{\theta}_n-\theta$. Let $\hat{\theta}^*_{n,1},...,\hat{\theta}^*_{n,B}$ denote bootstrap replications of $\hat{\theta}_n$. Let $H(r)$ denote the CDF of the pivot
$$H(r)=\mathbb P_F(R_n\le r)$$
Define $C^*_n =(a,b)$ as the [[Models, Statistical Inference and Learning#Confidence Sets|confidence interval]] where:
$$a=\hat{\theta}_n-H^{-1}\left(1-\frac{\alpha}{2}\right)\quad \text{and}\quad n=\hat{\theta}_n-H^{-1}\left(\frac{\alpha}{2}\right)$$
hence $C^*_n$ is an exact $1-\alpha$ confidence interval for $\theta$. Unfortunately, $a$ and $b$ depend on the unknown distribution $H$ but we can form a bootstrap estimate of $H$
$$\hat{H}(r)=\frac{1}{B}\sum^B_{b=1}I(R^*_{n,b}\le r)$$
where $R^*_{n,b}=\hat{\theta}^*_{n,b}-\hat{\theta}_{n}$. Let $r_{\beta}^*$ denote the $\beta$ sample quantile of $(R^*_{n,1},...,R^*_{n,B})a$ and let $\theta^*_{\beta}$ denote the $\beta$ sample quantile of $(\hat{\theta}^*_{n,1},...,\hat{\theta}^*_{n,B})$. Note