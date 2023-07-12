---
tags:
- programming/machine-learning/meta-learning
- research/paper-notes
- ruff-note
---
[[Meta Learning|Meta]] [[Reinforcement Learning]] can be broadly described as learning a part or all of an RL algorithm.
# Formalisation
Where RL learns a policy, meta-RL learns the RL algorithm $f$ that outputs the policy. 

We generally parameterize $f_\theta$ with meta parameters$\theta$ and learn these parameters to maximize a meta-RL objective. Hence, $f_\theta$ outputs the parameters of $\pi_\phi$ directly:$\phi=f_\theta(\mathcal D)$. We refer to the policy $\pi_\phi$ as the base policy with base parameters $\phi$. Here, $\mathcal D$ is a meta-trajectory that may contain multiple policy episodes. Some meta-RL algorithms use $f_\theta$ to map $\mathcal D$ to $\phi$ at every MDP step, while others do so less frequently.



## Meta-RL objective
The performance of a meta-RL algorithm is measured in terms of the returns achieved by the policy $\pi_\phi$ produced by the inner loop on tasks $\mathcal M$ drawn from the task distribution.

Depending on the application, slightly different objectives are considered. For some applications, we can afford a burn-in or adaptation period, during which the performance of the policies produced by the inner-loop is not important as long as the final policy found by the inner loops solves the task. The episodes during this burn-in  phase can be used by the inner loop for freely exploring the task. For other applications a burn-in period is not possible and correspondingly the agent must maximize the expected return from the first timestep it interact with the environment.

Maximizing these different objectives leads to different Learned exploration strategies: a burn-in enables more risk-taking at the cost of wasted training resources when the risks are realized. Formally, the meta-RL objective for both settings is:
$$\mathcal J(\theta)=\mathbb E_{\mathcal M^i\sim p(\mathcal M)}\left[\mathbb E_\mathcal D\left[\sum_{\tau\in\mathcal D_{K:H}}G(\tau)\bigg\vert f_\theta,\mathcal M^i\right]\right]$$
Where $G(\tau)$ is the discounted return in the MDP $\mathcal M^i$ and $H$ is the length of the trial, or the task horizon. The burn-in period is captured by $k$, which is the index of the first episode during the trial in which return counts towards the objective.$K=0$ corresponds to no burn-in. The episodes $\tau$  are sampled from the MDP$\mathcal M^i$ with the policy $\pi_\phi$, whose parameters are produced by the inner-loop $f_\theta(\mathcal D)$.

## Problem Categories
While the given problem setting applies to all of meta-RL, distinct clusters in the literature have emerged based on two dimensions:
1. Whether the task-horizon $H$ is short (a few episodes) or long (hundreds of episodes or more)
2. Whether the task distribution $p(\mathcal M)$ contains multiple tasks or just one. 

This creates four clusters of problems, of which three yield practical algorithms.

### Few Shot Multi Task Setting
In this setting, an agent must quickly, within just a few episodes, adapt to a new MDP sampled from the task distribution it was trained on. This requirement captures the central idea in meta-RL that we want to use the task distribution to train agents that are capable of learning new tasks from that distribution using as few environment interactions as possible. The shots in the name of the setting echo the shots in few-shot classification, where a model is trained to recognize new classes given only a few samples from each. In meta-RL, the number of burn-in episodes $K$ is more or less analogous to the shots in classification. 

While few-shot adaptation directly tackles the motivating question for meta-RL, sometimes the agent faces an adaptation problem so difficult that it is unrealistic to hope for success within a small number of episodes. This might happen, for example, when adapting to tasks that do not have support in the task distribution. In such cases, the inner-loop may require thousands of episodes or more to produce a good policy for a new task, but we would still like to use meta-learning to make the inner-loop as data efficient as possible. 

Meta-RL is