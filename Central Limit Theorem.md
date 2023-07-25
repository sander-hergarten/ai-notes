---
tags:
- math/statistics
aliases:
- central limit theorem
- CLT
---
Suppose that $X_1,...,X_n$ are IID with mean $\mu$ and variance $\sigma$. The central limit theorem says that $\overline{X}_n=n^{-1}\sum_i X_i$ has a distribution which is approximately [[Normal Distribution|normal]] with mean $\mu$ and variance $\sigma^2/n$. This is remarkable since nothing is assumed about the distribution of $X_i$, except the existence of the mean and variance.

>[!quote] Theorem (The Central Limit Theorem)
>Let $X_1,...,X_n$ be IID with mean $\mu$ and variance $\sigma^2$. Let $\overline{X}_n=n^{-1}\sum^n_{i=1} X_i$. Then $$Z_n\equiv\frac{\sqrt{n}(\overline{X}_n-\mu)}{\sigma}\rightsquigarrow Z$$ 
>where $Z\sim N(0,1)$. In other words,
>$$\lim_{n\rightarrow\infty}\mathbb P(Z_n\le z)=\Phi(Z)=\int^z_{-\infty}\frac{1}{\sqrt{2\pi}}e^{-x^2/2}dx$$ 

Interpretation: Probability statements about $\overline{X}_n$ can be approximated using a Normal distribution. It's the probability statement that we are approximating, not the random variable itself

In addition to $Z_n\rightsquigarrow N(0,1)$, there are several forms of notation to denote the fact that the distribution of $Z_n$ is converging to a Normal. They all mean the same thing:
$$\begin{align}
Z_{n}\;&\approx\;N(0,1)\\
\overline{X}_{N\;}&\approx\; N\left(\mu,\: \frac{\sigma^2}{n}\right)\\
\overline{X}_n-\mu\;&\approx\; N\left(0,\: \frac{\sigma^2}{n}\right)\\
\sqrt{n} (\overline{X}_n-\mu)\; &\approx\: N(0,\sigma^2)\\
\frac{\sqrt{n} (\overline X_{n}-\mu)}{\sigma}\;&\approx N(0,1)
\end{align}$$

We rarely know $\sigma$ but can estimate $\sigma^2$ from $X_1,...,X_n$ by 
$$S^2_n=\frac{1}{n-1}\sum^n_{i=1}(X_i-\overline{X}_n)^2$$
This raises the question if replacing $\sigma$ with $S_n$ keeps the central limit theorems truthness. The answer is Yes
>[!quote] Theorem
>Assume the same conditions as the CLT. Then,
>$$\frac{\sqrt{n}(\overline{X}_n-\mu)}{S_n}\rightsquigarrow N(0,1)$$

The accuracy of the normal approximation is given in the Berry-Essèen theorem.
>[!quote] Theorem (Berry-Essèen)
>Suppose that $\mathbb E|X_1|^3<\infty$. Then 
>$$\sup_z|\mathbb P(Z_n\le z)-\Phi(z)|\le\frac{33}{4}\frac{\mathbb E|X_1-\mu|^3}{\sqrt{n}\sigma^3}$$

There is also a multivariate version of the central limit theorem
>[!quote] Theorem (Multivariate central limit theorem)
>Let $X_1,...,X_n$ be IID random vectors where 
>$$X_i=\begin{bmatrix}
>X_{1i}\\
>X_{2i}\\
>\vdots \\
>X_{ki}
>\end{bmatrix}
>$$
>where mean
>$$\mu=\begin{bmatrix}\mu_1\\\mu_2\\\vdots\\\mu_k\end{bmatrix}=\begin{bmatrix}\mathbb E(X_{1i}\\\mathbb E(X_{2i})\\\vdots\\\mathbb E(X_{ki})\end{bmatrix}$$
>and variance matrix $\sum$. Let
>$$\overline{X}=\begin{bmatrix}\overline{X}_1\\ \overline{X}_2\\\vdots\\\overline{X}_k\end{bmatrix}$$
>where $\overline{X}_i=n^{-1}\sum^n_{i=1} X_{1i}$. Then,
>$$\sqrt{n}(\overline{X}-\mu)\rightsquigarrow N(0,\Sigma)$$
