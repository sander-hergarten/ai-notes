Let $X,Y,Z$ be discrete random variables. We say that $X$ and $Y$ are conditionally independent given $Z$ written $X\perp \!\!\! \perp Y|Z$, if
$$\mathbb P(X=x,Y=y|Z=z)=\mathbb P(X=x|Z=z)\mathbb P(Y=y|Z=z)$$
for all $x,y,z$. If $X,Y,Z$ are continuous random variables, we say that $X$ and $Y$ are conditionally independent given $Z$ if 
$$f_{X,Y|Z}(x,y|z)=f_{X|Z}(x|z)f_{Y|Z}(y|z)$$
for all $x, y, z$

Intuitively, this means that, once you know $Z$, $Y$ provides no extra information about $X$.

The conditional independence relation satisfies some basic properties:
![[Pasted image 20230625194640.png]]

The last properties requires the assumption that all events have positive probability; the first four do not.