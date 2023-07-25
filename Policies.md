---
tags:
- programming/machine-learning/reinforcement-learning
aliases:
- policy
- policies
- Policy
---
A Policy is like an instruction list that tells an agent what actions to take. It can be deterministic in which case it is denoted by
$$a_t = \mu(s_t) $$ or stochastic:
$$a_t \texttildelow \pi(\cdot|s_t) $$
In deep RL these are **parameterized policies** whose outputs are computable functions that depend on a set of parameters which we can adjust to change the behavior via some optimization algorithm. This is for example the weights and biases. 

Often these parameters are denoted with $\theta$ or $\phi$ 


# Deterministic Policies
A deterministic policie can easily be expresed as a normal function that takes the observations as inputs and returns the actions

```py
network = Sequential(
			layers.Dense(64, "relu", input_size="obs_dim")
			layers.Dense(128, "relu")
			layers.Dense(120, "tanh")
		)

actions = network(observations)

```

# Sochastic Policies
Stochastic Policies usualy come in 2 flavors:
1. Categorical policies for discrete action space 
2. Diagonal Gaussian policies for continuous action spaces

Computing the actions given a state from the policy is more difficult just as computling Log Likelihoods of particular actions. 

## Categorical  Policies
A categorical policy is built like a classifier over all actions. the input is the observation. 

**Sampling** Given the probabilities for each action PyTorch and Tensorflow have built in tools for sampling. 

**Log Likelihood** Denote the last layer of probabilities as $P_{\theta}(s)$, which is a vector with howevermany ellements as there are actions, so that the actions can be treated as indecies of the vector. The log likelihood fopr an action a can then be obtained by indexing into the vector:
$$\log{\pi(a|s)} = \log{\left[ P_{\theta}(s)\right]_a}$$
This means the log likelihood for a given action is the logarithm of the corresponding index at the output layer.

## Diagonal Gauss Policies
