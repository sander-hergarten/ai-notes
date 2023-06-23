Plan trajectories from raw image observations. Bellman based a

to arrive at an optimal solution we turn to the technique of collocation which optimizes a sequecne of states to maximize the reward. this is done while also eventually ensuring dynamics feasibility by recovering the corresponding actions in a constrained optimisation problem:
find the sequence which returns the states that provide the maximum amount of reward.

$$\textbf{max}\sum_t r(s_t)\quad \textbf{s.t.}\quad  s_{t+1}=f(s_t,a_t)$$
The latent dynamics distribution should then reflect the stochasticity in the observed data.
$$p_{\phi}(z_{t+1}|z_t,a_t)$$
To train this model the likelihood of the observedd data is maximized $r_{1:T}, o_{1:T}$. while maximizing exact likelihood is to hard a variational lower bound is trained using a variational distribution 
$$q_{\phi}(z_{t+1}|o_{t+1}, a_t, z_t)$$ 

LatCo creates 


# Intuition
Latent collocation tries to circumvent the shortsightedness that occurs through the bellman equation discount factor.

This is done by the following:
$$\max \sum_tr(s_t)$$
with following definitions:
- $r$ a function that gets a markovian state and outputs a  reward for that state.
- $s_t$ a markovian state at timestep $t$

to generate a markovian state from observations the technique of latent collocation is used. 

For this 2 dynamics models are made:
1. $p_\phi(z_{t+1}\vert z_t, a_t)$ 
2. $q_{\phi}(z_{t+1}\vert o_{t+1},a_t, z_t)$ 
both of these dynamics models are treated as stochastic probability density functions. This enables the technique of [[Moment Matching]] between $p_{\phi}$ and $q_{\phi}$. The objective changes with this formulation to:
$$\max_{a_{1:T-1}}\ \mathbb E_{p_\phi(z_{t+1}\vert z_t, a_t)}\left[\sum_tr(z_t)\right]$$
this can be optimized by recursively calculating the $z$-state, called shooting, as done in prior work such as in [Underactuated Robotics](https://underactuated.csail.mit.edu/index.html) but this is known to be poorly conditioned due to the recursive application of dynamics, which results in hard credit assignment.

LatCo formulates the trajectory optimization problem as a constrained optimization problem. To do this the authors define it abstractly as optimizing a sequence of distributions $q(z_t)$, each representing an uncertain estimate of what the latent $z_t$ will be at time $t$:
$$\max_{q(z_{2:T}),a_{1:T-1}}\ \sum_t\mathbb E_{q(z_t)}\ [r(z_t)]$$
where we constrain:
$$\begin{align}
& q(z_{t+1})=\mathbb E_{q(z_t)}p_{\phi}(z_{t+1}\vert z_t,a_t)\\
& q(z_1)=p(z_1)
\end{align}$$
when the constraint is satisfied this is equivalent to the original problem. We can use [[Moment Matching]] or a [[Bergman Divergence]] to express the constraint. When using Moment matching, assuming both distributions are Gaussian with 2 moments,  the constraint is changed to:
$$\begin{align}
&mean[p(z_t)]=mean[q(z_t)]\\
&var[p(z_t)]=var[q(z_t)]
\end{align}$$
where we denoted with some abuse of notation $p(z_{t+1})=\mathbb E_{q(z_t)}p_{\phi}(z_{t+1}\vert z_t,a_t)$. Further moments can be used for distributions with more degrees of freedom.

This leads us to the two cases the authors introduced to describe LatCo:
- Deterministic LatCo
- LatCo with Gaussian Plans

## Deterministic
The distribution $q(z_{2:T})$ is represented using [[Distributions|particles]] $z_{2:T_i}^i$. In practice they use a single particle since a deterministic distribution only returns one value. This means the authors assume that $q(z_{2:T})$ is deterministic and as such can only describe deterministic environments. The moment matching constraint therefore reduces to a single constraint: 
$$mean[p_{\phi}(z \vert z_{t-1}, a_{t-1})]=z_t$$
The variance constraint disappears since the variance of a set of one particle is a constant. this constraint, for $\mu_{\phi}(z_t,a_t)=\mathbb E_{p_{\phi}(z_{t+1}\vert z_t,a_t)} [z_{t+1}]$, yields a simplified planning problem:
$$\begin{align}
 \max_{z_{2:T},a_{1:T-1}}\ &\sum_tr(z_t)\\
 \text{constrained by}\quad  &z_{t+1}=\mu_{\phi}(z_t, a_t)
\end{align}
$$
This approximation is equivalent to using the deterministic expected value from the underlying dynamics model and performing standard [[Deterministic Collocation]]. This is a common assumption and is known as the certainty equivalence principle, and has appealing properties for certain kinds of distributions. Other approximations with a single particle are possible, such as maximizing the likelihood of the particle, but these require introduction of additional hyperparameters.


## Non-Deterministic
To represent uncertainty a more expressive distribution has to be used. Speciffically, since the latent dynamics $p_{\phi}(z_{t+1}\vert z_t, a_t)$ follow a Gaussian distributionm q is parametrized as a diagonal covariance Gaussion $q(z_{1:T}) = \mathcal N(\mu_{1:T},\sigma^2_{1:T})$. More expressive distributions can be used, but we observed that diagonal-covariance Gaussian already yields good performance on stochastic environments. 

To evaluate the moment matching constraint $\mu, \sigma^2$ is ussed directly for the mean and variance of $q(z_t)$ while the mean and variance of $p(z_t)$ are estimated with samples. Gradients are estimated with [[Reparametrization]] and 50 samples.


# Loss and Optimization
Under some reformulation, it is possible to reformulate the equivalent dual constrained return maximization, as the saddle point problem on the Lagrangian:
$$\min_{\lambda}\max_{q(z_{2:T}),a_{1:T-1}}\ \sum_t\mathbb E_{q(z_t)}\ [r(z_t)]\ -\lambda(\|mean[p(z_t)]-mean[q(z_t)]\|^2-\epsilon)-\lambda(\|var[p(z_t)]-var[q(z_t)]\|^2-\epsilon)$$
