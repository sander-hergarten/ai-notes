# Description 
Bayesian optimization is a suite of techniques often used to tune Hyperparameters. Bayesian Optimization can be used to optimize any black-box function.

While active learning has the ability to represent the true underlying function, it is less sample efficiant than Bayesian Optimization which just desires to find the maxima/minima.


## Bayes' theorem

$$\begin{align}
P(H|E)&=\frac{P(H)P(E|H)}{P(E)}\\
\\
P(E)&=P(H)P(E|H)+P(\neg H)P(E|\neg H)
\end{align}
$$

You begin with a case $E$ over a sample $H$. The Probability of $E$ occuring in $H$ is described by $P(E|H)$. While the Probability 