---
tags:
- programming/machine-learning/meta-learning
- ruff-note
aliases:
- MAML
- maml
- model agnostic meta learning
- model-agnostic meta-learning
---
MAML is an influential design following this pattern. Its inner-loop is a policy gradient algorithm whose initial parameters are the meta-parameters $\phi_0=\theta$. The key insight is that such an inner-loop is a differentiable function of the initial parameters, and therefore the initialization can be optimized with gradient descent to be a good starting point for learning on tasks from the task distribution . When adapting to a new task, MAML collects data using the initial policy and computs an updated set of parameters by applying a policy gradient step for a task $\mathcal M^i \sim p(\mathcal M)$:
$$\phi^i_1=f(\mathcal D^i_0,\phi_0)=\phi_0+\alpha\nabla_{\phi_0}\hat J(\mathcal D ^i_0,\pi_{\phi_0})$$
where $\hat J(\mathcal D ^i_0,\pi_{\phi_0})$ is an estimate of the returns of the policy $\pi_{\phi_0}$ for the task $\mathcal M^i$  and $\alpha$ is the learning rate. Difficult tasks may require multiple gradient steps in the inner-loop, MAML computes the gradient of the returns of the updated policy with respect to the initial parameters:
$$\phi'_0=\phi_0+\beta\nabla_{\phi_0}\sum_{\mathcal M^i\sim p(\mathcal M)} \hat J(\mathcal D ^i_0,\pi_{\phi_0})$$
where $\pi ^i_{\phi_1}$ is the policy for task $i$ updated once by the inner-loop, $\beta$ is a learning rate, and $\nabla_{\phi_0}\hat J(\mathcal D ^i_0,\pi^i_{\phi_1})$  is the gradient of the returns of the updated policy computed w.r.t. the initial policy parameters. Such a gradient through an RL inner-loop is often referred to as a meta-gradient. Descending the meta-gradient corresponds to optimizing the outer-loop objective.

# Why MAML is Model-Agnostic
Metric-based and Model-based approaches force constraints on either the sampling or the model's architecture. MAML, on the other hand requires the model to be optimizable by a gradient-based optimizer. 

The neural network is designed the same way your usual model might be. All the magic happens during optimization. As a consequence, unlike metric based and model based approaches, MAML lets you choose the model architecture freely. This has the benefit of being applicable to reinforcement learning.

# How MAML works
The normal optimization steps for a gradient descent system can be described as 
$$\begin{align}
\min_\phi\mathcal L_\tau(\phi)\\
s.t.\; \phi\leftarrow\phi-\alpha\nabla_\phi\mathcal L_\tau(\phi)
\end{align}$$
The key idea of MAML is to mitigate the problem of this requiring many datapoints for each task $\tau$ by learning not only from the data regarding exactly our task but also from data of similar tasks. We make the additional assumption that $\tau_i\sim p(\tau)$. $\tau$ is now a random variable and $\phi_\tau$ is a set of parameters for task $\tau$. we may use different parameters for each task, use the same parameters for every task, or do something in between.

Additionally, we will not simply use the data from other tasks to find parameters that are optimal for all tasks, but keep the option to fine-tune our model, i.e., take additional optimizer
