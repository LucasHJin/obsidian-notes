2025-12-20 00:37

Status:


Tags:
[[cs]] 
[[ai]] 
[[rl]] 
[[ml]] 


_______
# RL - Training Strategies

Relates to [[RL - Value Based Methods]] and [[RL - Q Learning]] 

**Monte Carlo** → train the value/policy function using an entire episode
- *Remember → episode is an entire run through of the game* 
- ![[Screenshot 2025-12-20 at 4.47.37 PM.png|400]] 
	- Use calculated reward as target for value/policy
	- Basically → “use what happened this time as to improve you guess of what happens in an average case”
		- In the case of state value for example → will find total sum of rewards and then apply this to each possible state
		- Only updates visited states

**Temporal Difference** → trains using one step (St,At,Rt+1,St+1)
- **Bootstrapping:** estimate overall return $G_t$ by adding $R_{t+1}$ and the discounted value of the next state (estimation)
	- ![[Screenshot 2025-12-20 at 4.53.27 PM.png|400]] 
	- Still works similar to MC but it instead replaces calculated return with an estimation ([[RL - Value Based Methods|Bellman]]) 
- *Note* → can work over non-ending episodes / repeated episodes

^ Has a tradeoff between bias and variance
- MC → higher variance (because of stochastic policy)
- TD → higher bias (value estimation depends on old networks / estimates)


# References

