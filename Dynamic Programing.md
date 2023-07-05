The term dynamic programming refers to a collection of algorithms that can be used to compute optimal policies given a perfect model of the environment as a Markov decision process.

We usually assume that the environment is a finite MDP. That is we assume that its state, action, and reward sets, are finite, that its dynamics are given by a set of probabilities $p(s',r|s,a)$. Although DP ideas can be applied to problem with continuous state and action spaces, exact solutions are usually not possible.

The key idea of DP, and of reinforcement learning generally, is the use of value functions to organize and structure the search for good policies.

We can easily obtain [[Optimal Policies and Value Functions#Optimal Policies|optimal policies]] once we have found the [[Optimal Policies and Value Functions#Optimal Value function|optimal value functions]] which satisfy the[[Optimal Policies and Value Functions#Bellman Optimality Equation|Bellman optimality equation]]. 

DP algorithms are obtained by turning Bellman equations into assignments, that is, into update rules for improving approximations of the desired value functions.

# Prediction Problem
We To compute the state-value function $v_\pi$ for an arbitrary policy $\pi$. we
