2025-12-19 00:39

Status:


Tags:
[[cs]] 
[[ai]] 
[[rl]] 
[[ml]] 
[[dl]] 


_______
# RL - Deep RL Basics

To know → [[RL Basics]] 

**Parameterized policies:** policies whose outputs are computable functions that depend on a set of parameters (can adjust with optimization algorithms)
- Is how you adapt policy based methods to deep learning
- Stochastic DL Examples:
	- **Categorical policies** → used for discrete action spaces
		- Like a classifier NN where you use softmax (converts to decimals adding to 1) on logits from last layer
	- **Diagonal Gaussian policies** → used in continuous spaces
- *Note*:
	- Need to sample actions from policy,
	- Need to compute `log` likelihood of actions
- **Categorical policies:** 

**Value functions:** provides value given a starting state / state-value pair and then acting according to a certain policy
- *Note* → only takes time as an argument for finite horizon returns
- **On-policy Value function** → start at s, use policy π
	- $V^{\pi} (s)$ 
- **On-policy Action Value function** → start at s, take action a, then use policy π
	- $Q^{\pi} (s, a)$ 
- **Optimal Value function** → start at s, use optimal policy π in the environment
	- $V^{*} (s)$ 
- **Optimal Action Value function** → start at s, take action a, then use optimal policy π in the environment
	- $Q^{*} (s, a)$ 

**Bellman equations:** The value of your starting point is the reward you expect to get from being there, plus the value of wherever you land next.
- **Bellman backup:** reward plus next value

**Advantage function:** describes how much better it is to take a specific action a in state s, over randomly selecting an action according to $\pi(\cdot|s)$, assuming you act according to $\pi$ forever after
- ![[Screenshot 2025-12-19 at 12.00.15 PM.png]] 

**Markov Decision Processes (MDP):** mathematical way of describing agent environment
- ![[Screenshot 2025-12-19 at 12.02.00 PM.png]] 

# References
https://spinningup.openai.com/en/latest/spinningup/rl_intro.html
