# Markov and Chebychev Inequalities
Inequalities are useful for bounding quantities that might otherwise be hard to compute. 
>[!quote] Theorem (Markov's Inequality.) 
>Let $X$ be a non-negative random variable and suppose that $\mathbb E(X)$ exists. For any $t>0$,
>$$\mathbb P(X>t)\le \frac{\mathbb E(X)}{t}$$

>[!quote] Theorem (Chebyshev's inequality) 
>Let $\mu =\mathbb E(X)$ and $\sigma^2=\mathbb V(X)$. Then,
>$$\mathbb P(|X-\mu|\ge t)\le\frac{\sigma^2}{t^2}\quad\text{and}\quad\mathbb P(|Z|\ge k)\le\frac{1}{k^2}$$
>where $Z=(X-\mu)/\sigma$. In particular $\mathbb P(|Z|>2)\le 1/4$ and $\mathbb P(|Z|>3)\le 1/9$

# Hoeffding's Inequality 
Hoeffding's inequality is similar in spirit to Markov's inequality but it is a sharper inequality. We present the result here in two parts. 
> [!quote] Theorem
> Let $Y_1,...,Y_n$ be independent observations such that $\mathbb E(Y_i)= 0$ and  $a_i\le Y_i \le b_i$. Let $\sigma > 0$. Then, for any $t>0$,$$\mathbb P\left(\sum^n_{i=1}Y_i\ge\sigma\right)\le e^{-t\epsilon}\prod^n_{i=1}e^{t^2(b_i-a_i)^2/8}$$

>[!quote] Theorem
>Let $X_1,...,X_n\sim$ Bernoulli($p$). Then, for any $\epsilon>0$,
>$$\mathbb P(|\overline{X}_n-p|>\epsilon)\le2e^{-2n\epsilon^2}$$
>where $\overline{X}_n=n^{-1}\sum^n_{i=1}X_i$

Hoeffding's inequality gives us a simple way to create a confidence interval for a binomial parameter $p$. Here is the basic idea. Fix $\alpha>0$ and let 
$$\epsilon_n=\left\{\frac{1}{2n}log\left(\frac{2}{\alpha}\right)\right\}^{1/2}$$
By Hoeffding's inequality,
$$\mathbb P(|\overline{X}_n-p|>\epsilon_n)\le 2e^{-2n\epsilon^2_n}=\alpha$$
# Cauchy-Schwarz and Jensen Inequality
>[!quote] Theorem (Cauchy-Schwarz inequality)
>If $X$ and $Y$ have finite variances then $$\mathbb E|XY|\le\sqrt{\mathbb E(X^2)\mathbb E(Y^2)}$$


Recall that a function $g$ is convex if for each $x, y$ and each $\alpha \in [0,1]$,
$$g(\alpha x+(1-\alpha)y)\le \alpha g(x)+(1-\alpha)g(y)$$
If $g$ is twice differentiable, then convexity reduces to checking that $g''(x)\ge 0$ for all $x$. It can be shown that if $g$ is convex then it lies above any line that touches $g$ at some point, called a tangent line. A function $g$ is concave if $-g$ is convex. Examples of convex functions are $g(x)=x^2$ and $g(x)=e^x$.
>[!quote] Theorem (Jensen's Inequality)
>If $g$ is convex then 
>$$\mathbb Eg(X)\ge g(\mathbb EX)$$
>if $g$ is concave:
>$$\mathbb Eg(X)\le g(\mathbb EX)$$

