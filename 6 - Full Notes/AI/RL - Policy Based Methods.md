2025-12-23 00:39

Status:


Tags:
[[cs]] 
[[ai]] 
[[rl]] 
[[ml]] 
[[dl]] 


_______
# RL - Policy Based Methods

**Policy based methods:** remember [[RL - Value Based Methods]] 
- Want to directly approximate policy without learning a value function
- **[[DL - Activation Functions|Parameterize the policy]]** → represent the policy using adjustable parameters theta (no fixed rule)
	- i.e. a neural network gives a probability distribution for actions (stochastic)
	- Want to maximize performance (reward) with gradient ascent
	- **Gradient ascent:** using gradient to get to highest point
	- ![[Screenshot 2025-12-23 at 12.48.00 AM.png|500]] 
		- Need to control $\theta$ that affects distribution of actions over a state
		- I.e. weights, coefficients of NN, etc.
	- ![[Pasted image 20251223004929.png|500]] 
- **GOAL:** Define objective function $J(\theta)$ → find $\theta$ that optimizes this
- *Note* → optimization is mostly [[RL - Q Learning|on policy]] (for each update, use only data collected by most recent version of $\pi_{\theta}$) 

**Policy based vs [[RL - Policy Gradient Methods|Policy gradient]]:** 
- PG is a subclass of policy based 
- **Difference: how to optimize $\theta$** 
	- Policy based → optimize parameter $\theta$ indirectly by maximizing the local approximation of the objective function
		- Try a value, change it slightly, compare results 
		- I.e. hill climbing, simulated annealing, or evolution strategies
	- Policy gradient → optimize parameter $\theta$ directly by performing gradient ascent on objective function performance
		- Know which direction to change $\theta$ and effect of each parameter
 


# References

