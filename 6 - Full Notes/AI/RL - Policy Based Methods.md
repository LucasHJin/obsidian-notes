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
- **Parameterize the policy** → i.e. a neural network gives a probability distribution for actions (stochastic)
	- Want to maximize performance (reward) with gradient ascent
	- **Gradient ascent:** using gradient to get to highest point
	- ![[Screenshot 2025-12-23 at 12.48.00 AM.png|500]] 
		- Need to control $\theta$ that affects distribution of actions over a state
		- I.e. weights, coefficients of NN, etc.
	- ![[Pasted image 20251223004929.png|500]] 
		- 



# References

