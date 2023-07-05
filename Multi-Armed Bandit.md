The Multi Armed Bandit is a [[value-based]] RL agent.

Consider the following learning problem. You are faced repeatedly with a choice among $k$ different options or actions. After each choice you receive a numerical reward chosen from a stationary probability distribution that depends on the action you selected.

Through repeat action selection s you are to maximize your winnings by concentrating your actions on the best levers(actions). 

In the $k$-armed bandit problem, each of the $k$ actions has an expected or mean reward given that that action is selected.
$$q_*(a)=\mathbb E[R_t|A_t=a]$$
where $A_t$ and $R_t$ are the action selected and reward received at $t$i

When training multi armed bandits we develop an estimator for $q_*$ called $Q_t$ which is also reffered to as a value function.

