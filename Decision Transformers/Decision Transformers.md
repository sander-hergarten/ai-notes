# Abstract
Decision Transformers attempt to create a sequence modeling problem out of an RL problem. This makes it possible to use transformers to solve them. The transformer is not required to learn value functions or compute policy gradients. Instead they condition a Transformer

# Mechanism
the transformer input is a trajectory made up of $$step=(\hat{R}, s,a,t)$$
$\hat{R}$ is the reward to go and is used as a query argument
$s$ is the state encoded
$a$ is the action
$t$ is the timestamp for temporal encoding 

The model is capable of extrapolating the steps in an autoregressive manor. This is done using a transformer implementation in the style of the GPT models.


# Implementation Details

# Contributions

# Key Takeaways
It is possible to create an algorithm capable of diverse imitation learning with this technique. 