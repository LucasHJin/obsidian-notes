2025-09-25 22:17

Status:


Tags:
[[rl]] 
[[cs]] 
[[ai]] 
[[uni]] 
[[ml]] 


_______
# RL Basics

**Reinforcement learning:** training an AI where it interacts with the environment and receives rewards (pos/neg) as feedback
![[Pasted image 20250926113448.png|400]] 
- Want to maximize cumulative reward (expected return)
- **State:** full description of state of the world
- **Observation:** partial description of the state
- **Discrete space:** finite amount of actions
- **Continuous space:** infinite amount of actions
- **Rewards + Discounting** → to reduce reward of future actions because they are less likely to happen (further away)
	- ![[Pasted image 20250926113739.png]] 
	- discount = 0.95 to 0.99
- **Episodic task:** has a start and an end
- **Continuing task:** continues forever
	- Need to learn to choose best actions while simultaneously interacting with environment

**Exploration/Exploitation tradeoff:** 
- **Exploration:** exploring environment with random actions to get more info about environment
- **Exploitation:** using known information to maximize reward
- Could pick something guaranteed to be good but exploring could lead to something even better

**Main approaches:** policy π → brain of the agent (defines the action to take given state)
- Want to find the optimal policy π* to maximize return (with training)
	- **Policy based methods:** directly teaching the agent given current state
		- **Deterministic:** a policy at a given state will always return the same action
			- ![[Screenshot 2025-09-26 at 11.52.17 AM.png]] 
		- **Stochastic:** outputs a probability distribution over actions
			-  ![[Screenshot 2025-09-26 at 11.51.48 AM.png]] 
	- **Value based methods:** teaching the agent to learn which state is more valuable and taking values to get there
		- learn a value function that maps a state to the expected value of being at that state
			- Value of a state → expected discount return if starting at that state (then act according to policy → go to state with highest value)
			- ![[Screenshot 2025-09-26 at 11.53.42 AM.png]] 

**Deep RL:** using deep neural networks instead of traditional algorithms to solve RL problems
- ![[Pasted image 20250926133500.png]] 
**Stable Baselines 3:** a set of reliable implementations of reinforcement learning algorithms in PyTorch
- *Setup steps:*
	- Create environment
	- Define and instantiate desired model
	- Train agent with `model.learn` + total amount of training timesteps
	- Evaluate the agent → `evaluate_policy` 
**Proximity Policy Optimization (PPO):** state of the art deep reinforcement learning algorithm
- Combination of value-based RL and policy-based RL



# References
https://huggingface.co/learn/deep-rl-course/unit1/introduction
