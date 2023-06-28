 [[Markov Properties]]
Hyper Markov Properties  enable the parameterisation and estimation of graphical models. These state that the parameters should exhibit [[Conditional Independence]], similar to those on the sample space. When these properties are satisfied, parameter estimation may be performed locally that is the estimators for certain subsets of the graph are determined entirely by the data corresponding to the subset.

# Definition
We define a model to be a family of probability distributions $\Theta$ over a common measurable space. Specifically, we will focus on the case where $\Theta \subseteq \mathfrak P(\mathcal G)$, the set of distribtuions that are Markov with respect to a graph $\mathcal G$. 

For any $\theta\in\Theta$ and $A\subseteq V$, define $\theta_A$ to be the marginal distribution of $X_A$ under $\theta$.

Moreover, for $A,B\subseteq V$, we define $\theta_{A|B}$ to be the family of conditional distributions of $(X_A|X_B=x_b)_{x_b}$. If we use $\phi\simeq\psi$ to denote the existence of a bijective function between $\phi$ and  $\psi$, we note that for any $A\subseteq V$ 
$$\theta\simeq(\theta_A,\theta_{V\backslash A|A})$$
A law $\textsterling$  is a probability distribution of a random distribution $\tilde\theta$ taking values in $\Theta$. 

## Weak Hyper Markov
A law $\textsterling(\tilde\theta)$ for an undirected graph $\mathcal G$ is weak hyper hyper Markov if for any decomposition $(A,B)$ of $\mathcal G$:
$$\tilde\theta_A\perp\!\!\!\perp\tilde\theta_B|\tilde\theta_{A\cap B}$$ Note that both weak Hyper Markov Properties may be characterised in terms of their separoids:

A $\textsterling(\tilde\theta)$ is a weak hyper markov with respect to an undirected decomposable or directed acyclic graph $G$ if and only if:
$$\tilde\theta_{A\cup C}\perp\!\!\!\perp\tilde\theta_{A\cup C}|\tilde\theta_C$$
for all $\langle A,B|C\rangle \in\mathcal M(\mathcal G)$

As a consequence of this, if $\textsterling$ is hyper Markov with respect to $\mathcal G$, and $\mathcal E(\mathcal G)\subseteq \mathcal E(\mathcal G')$, then $\textsterling$ is hyper Markov with respect to $\mathcal G'$ 


## Strong Hyper Markov 
>[!abstract] Definition (Strong Hyper Markov Property)
>A law $\textsterling(\tilde\theta)$ is strong hyper Markov with respect to an undirected decomposable graph $\mathcal G$ if for any decomposition $(A,B)$ of $\mathcal G$:
>$$\tilde\theta_{B|A}\perp\!\!\!\perp\tilde\theta_A$$
>
>A law $\textsterling(\tilde\theta)$ is strong directed hyper Markov with respect to a directed acyclic graph $\mathcal G$ if for every vertex $v\in V$:
>	$$\tilde\theta_{v|pa(v)}\perp\!\!\!\perp\tilde\theta_{}$$


