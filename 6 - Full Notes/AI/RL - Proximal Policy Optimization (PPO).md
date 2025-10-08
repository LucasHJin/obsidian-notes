2025-10-06 21:54

Status:


Tags:
[[rl]] 
[[cs]] 
[[ai]] 
[[ml]] 


_______
# RL - Proximal Policy Optimization (PPO)

**Proximal Policy Optimization (PPO):** an architecture that improves our agent’s training stability by avoiding policy updates that are too large
- Uses ratio comparing previous and current policy clamped to $[1+\epsilon, 1-\epsilon]$ 
- *REMEMBER:* **policy** is the brain of the model that decides the action based on state

**Reasoning:** 
- Smaller policies are more likely to converge to optimal solution
- Too big policies can lead to bad policies (make it harder to revert)
- ![[Pasted image 20251006215856.png|200]] 

**Problem with [[RL - Reinforce Algorithm|Reinforce]]:** 
- Step size → either too slow or too much variation
- **Clipped surrogate objective function** → new objective function that constrains policy change to a small range
	- ![[Pasted image 20251006220902.png]] 
		- **Ratio (rt)** → probability of taking a certain action at a certain state for current and previous policy
			- If >1 → more likely to make action now
		- Constrain by clipping the objective function by penalizing changes with a ratio far from 1
			- Epsilon is a hyper parameter → to be changed
- **When to update policy:** 
	- If ratio is in the range $[1-\epsilon, 1+\epsilon]$ 
	- Ratio is outside range but advantage leads towards the range
		- Below range + advantage > 0 (upwards gradient)
		- Above range + advantage < 0 (downwards gradient)
	- *Note:* 
		- **Gradient:** direction of change
		- **Advantage:** magnitude + sign of feedback


# References

https://huggingface.co/blog/deep-rl-ppo