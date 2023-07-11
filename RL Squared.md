---
tags:
- programming/machine-learning/reinforcement-learning
- programming/machine-learning/meta-learning
- research/paper-notes
- ruff-note
---

# RL$^2$ 
A popular approach to [[Meta Reinforcement Learning]] is to represent the inner-loop as an RNN and train it on tasks from the task distribution end-to-end with RL. In RL$^2$, the RNN not only looks at the previous states, but also at the previous actions and rewards allowing ti to adapt the policy on-the-go. The meta-parameters $\theta$ are the parameters for the RNN and other neural networks used in processing the inputs and outputs of $f_\theta$.

The inner loop parameters $\phi$ are the ephemeral hidden states of the RNN, which may change after ever timestep. 

The outer-loop objective is the expected discounted sum of rewards across the entire trial, which may consist of multiple episodes, instead of the standard RL objective that is the xpected return in a single episode. 

This corresponds to the [[Meta Reinforcement Learning#Meta-RL objective|meta-rl objective]] with $K=0$ up to differences in the discounting. To optimize this objective, RL$^2$ treats the trial as a single continuous episode, during which the RNN hidden state is not reset. The