Monte Carlo methods require only trajectories from acutal or simulated interactions with an environment. Learning from actual experience is striking because it requires no prior knowledge of the environments dynamics, yet can still attain optimal behavior. 
Monte Carlo methods are ways of solving the reinforcement learning problem based on averaging sample returns. To ensure that well defined returns are available, we define Monte Carlo methods only for episodic tasks. 

The term Monte Carlo is often used more broadly for any estimation method whose operation involves a significant random component. 

# Monte Carlo Prediction
An obvious way to estimate the state-value function for a given policy is simply to average the returns observed after visits to that state.

In particular, suppose we wish to estimate $v_\pi(s)$, the value for a state $s$ under policy $\pi$, given a set of episodes obtained by following $\pi$ and passing through $s$. Each occurrence of state $s$ in an episode is called a visit to $s$. Of course, $s$ may be visited multiple times in the same episode.