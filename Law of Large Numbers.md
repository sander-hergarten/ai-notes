---
tags:
- math/statistics
aliases:
- law of large numbers
- the law of large numbers
- 
---
This theorem says that the mean of a large sample is close to the mean of the distribution. 

Let $X_1,X_2,...$ be an IID sample and let $\mu=\mathbb E(X_1)$ and $\sigma^2=\mathbb V(X_1)$. Recall that the sample mean is defined as $\overline{X}_n=n^{-1}\sum^n_{i=1}X_i$ and that $\mathbb E(\overline{X}_n)=\mu$ and $\mathbb V(\overline{X}_n)=\sigma^2/n$ 
> [!quote] Theorem (The Weak Law of Large Numbers)
> If $X_1,...,X_n$ are IID, then $\overline{X}_n\xrightarrow{P}\mu$

Interpretation of WLLN: the distribution of $\overline{X}_n$ becomes more concentrated around $\mu$ as $n$ gets large