---
tags:
- programming/machine-learning/reinforcement-learning
---
The value function of a state $s$ under a policy $\pi$  denoted by $v_\pi(s)$, is the expected return when starting in $s$ and following $\pi$ thereafter. 

## State Value function
For MDP's we can define $v_\pi$ formally as:
$$v_\pi(s)=\mathbb E_\pi[G_t|S_t=s]=\mathbb E_\pi\left[\sum^\infty_{k=0}\gamma^kR_{t+k+1}\Bigg\vert S_t=s\right],\quad\text{for all $s\in\mathcal S$}$$
where $\mathbb E_\pi[\cdot]$ denotes the expected value of a random variable given that the agent follows policy $\pi$, and $t$ is any time step. We call the function  $v_\pi$ the state-value function for policy $\pi$

## Action Value function
Similarly, we define the value of taking action $a$ in state $s$ under a policy $\pi$, denoted $q_\pi(s,a), as the expected return starting from $s$, taking the action $a$, and there after following policy $\pi$
$$q_\pi(s,a)=\mathbb E_\pi[G_t|S_t=s,A_t=a]=\mathbb E_\pi\left[\sum^\infty_{k=0}\gamma^kR_{t+k+1}\Bigg\vert S_t=s,A_t=a\right],$$
## Monte Carlo Methods
Both the value functions can be estimated from experience.  If separate averages are kept for each action take in each state then these averages will similarly converge to the action values, $q_\pi(s,a)$. We call estimation methods of this kind [[Monte Carlo methods]] because they involve averaging over many random samples of actual returns.

## Recursive Relationships and The Bellman Equation
A fundamental property of dynamic programming is that they satisfy recursive relationships. For any policy $\pi$ and any state $s$, the following consistency condition holds between the value of $s$ and the value of its possible successor states;
$$\begin{align} 
v_\pi(s)&=\mathbb E_\pi[G_t|S_t]\\
&=\mathbb E_\pi[R_{t+1}+\gamma G_{t+1}| S_t=s]\\
&=\sum_a\pi(a|s)\sum_{s'}\sum_rp(s',r|s,a)\left[r+\gamma\mathbb E_\pi[G_{t+1}|S_{t+1}=s']\right]\\
&=\sum_a\pi(a|s)\sum_{s',r}p(s',r|s,a)[r+\gamma v_\pi(s')],\quad\text{for all $s \in \mathcal S$}
\end{align}$$
where it is implicit that the actions $a$ are taken from the set $\mathcal A(s)$, that the next states $s'$ are taken from the set $\mathcal S$ (or from $\mathcal S^+$ in the case of an episodic problem), and that rewards $r$ are taken from the set $\mathcal R$.

The final expression is really a sum over all values of the three variables $a, s', r'$. For each triple we compute its probability $\pi(a|s)p(s',r|s,a)$, weight the quantity in brackets by that probability, then sum over all possibilities to get an expected value.

This expression is also called the Bellman equation for $v_\pi$. It expresses a relationship between the value of a state and the values of its successor states. Think of looking ahead from a state to its possible successor states.

The Bellman equation averages over all the possibilities weighting each by its probability of occurring. It states that the value of the start state must equal the discounted value of the expected next state, plus the reward expected along the way.