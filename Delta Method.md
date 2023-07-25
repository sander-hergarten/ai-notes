---
tags:
- math/statistics
- ruff-note
---
If $Y_n$ has a limiting [[Normal Distribution]] then the delta method allows us to find the limiting distribution of $g(Y_n)$ where $g$ is any smooth function. This can be derived from the [[Central Limit Theorem|central limit theorem]]

> [!quote] Theorem (The Delta Method)
> Suppose that $$\frac{\sqrt{n}(Y_n-\mu)}{\sigma}\rightsquigarrow N(0,1)$$
> and that $g$ is a differentiable function such that $g'(\mu)\ne 0$. Then
> $$\frac{\sqrt{n}(g(Y_n)-g(\mu))}{|g'(\mu|\sigma)}\rightsquigarrow N(0,1)$$

In other words,
$$Y_n\approx N\left(\mu,\frac{\sigma^2}{n}\right)\; \Longrightarrow\; g(Y_n)\approx N\left(g(\mu),(g'(\mu))^2\frac{\sigma^2}{n}\right)$$
# The Multivariate delta function
> [!Danger] TODO

