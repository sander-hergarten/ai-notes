---
tags:
- programming/machine-learning/reinforcement-learning
- ruff-note
---
# Optimal Policies
Solving a Reinforcement learning task means, roughly, finding a [[Policies|policy]] that achieves a lot of reward over the long run. For finite MDP's we can precisely define an optimal policy in the following way. [[Value Functions|Value functions]] define a partial ordering over policies.
$$\pi\ge\pi'\quad\text{if}\quad v_\pi(s)\ge v_{\pi'}(s)\quad\text{for all $s\in\mathcal S$}$$ The optimal policy $\pi_*$ is defined as:
$$\pi_*=\pi\quad \text{if}\quad v_\pi(s)\ge v_{\pi'}(s)\quad\text{for all $s\in\mathcal S,\pi'\in\Pi$}$$
where $\Pi$ is the set of all possible policies. 

# Optimal Value function
As such all optimal policies share the same state-value function called the optimal state-value function $v_*(s)=\max_\pi v_\pi(s)$ and the same action value function called the optimal action-value function $q_*(s,a)=\max_\pi q_\pi(s,a)$ 

We can write $q_*$ in terms of $v_*$ as follows:
$$q_*(s,a)=\mathbb E[R_{t+1}+\gamma v_*(S_{t+1})|S_t=s,A_t=a]$$

# Bellman Optimality Equation

![[Pasted image 20230703170132.png]]
![[Pasted image 20230703170149.png]]
>[!Danger] Review page 86 of [[RLbook2020trimmed.pdf]] 

