All parametric models take the form 
$$\mathfrak{F} =\{f(x;\;\theta):\theta\in\Theta\}$$
Where $\Theta\subset \mathbb R^k$ is called the parameter space and $\theta=(\theta_1,...,\theta_k)$ an element or vector of elements making up the parameters. 

The problem of inference then reduces to the problem of estimating the parameter $\theta$

Using parametric inference requires knowing that the distribution that generated the data is in some parametric model. 

Parameters are called nuisance parameters if they are components of $\theta$ we are not interested in and parameters of interest if we are. The parameter of interest can be a complicated function of $\theta$.

For example:
Let $X_1,...,X_n\sim N(\mu,\sigma^2)$ The parameter is $\theta = (\mu, \sigma)$ is $\Theta=\{(\mu,\sigma):\;\mu\in\mathbb R,\;\sigma>0\}$. Suppose we are interested in $\tau$, the fraction who score above 1. Let $Z$ denote a standard Normal random variable $\frac{X-\mu}{\sigma}$ ![[Pasted image 20230621211944.png]]
The parameter of interest is $\tau=T(\mu,\sigma)=1-\Phi((1-\mu)/\sigma)$


