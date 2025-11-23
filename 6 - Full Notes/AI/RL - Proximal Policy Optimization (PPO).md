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
- *Essentially:* 
	- Actor-critic algorithm where updates are clipped so that new policies aren’t too far away from old ones

**Reasoning:** 
- Smaller policies are more likely to converge to optimal solution
- Too big policies can lead to bad policies (make it harder to revert)
- ![[Pasted image 20251006215856.png|200]] 

**Problem with [[RL - Reinforce Algorithm|Reinforce]]:** 
- Step size → either too slow or too much variation
- **Objective function:** function that maximizes/minimizes according to an objective/goal
- **Clipped surrogate objective function** → new objective function that constrains policy change to a small range
	-  ![[Screenshot 2025-10-08 at 11.02.59 AM.png]]
		- $L^{CLIP}$ → Loss function to be maximized
			- (how far the agent deviates from desired outcomes)
		- $E_t$ → empirical average over a batch of samples of timestamp t
			- $r_t$ (ratio) → probability of taking a certain action at a certain state for current and previous policy
				- If >1 → more likely to make action now
			- $\text{clip}(r_t(\theta),1-\epsilon,1+\epsilon)$ –> restricts the ratio to within a certain range
				- Epsilon is a hyper parameter → to be changed
			- $A_t$ (advantage) → tells us if the action was better or worse than average
				- Can compare how much better an action is compared to expectation OR how much better the reward is than expected (**TD error**) 
- **When to update policy:** 
	- If ratio is in the range $[1-\epsilon, 1+\epsilon]$ 
	- Ratio is outside range but advantage leads towards the range
		- Below range + advantage > 0 (upwards gradient)
		- Above range + advantage < 0 (downwards gradient)
	- *Note:* 
		- **Gradient:** direction of change
		- **Advantage:** magnitude + sign of feedback

![[Screenshot 2025-10-08 at 11.23.02 AM.png]] 

**Algorithm:** ![[Screenshot 2025-10-08 at 11.38.49 AM.png]]
- $L^{CLIP}$ → clipped policy improvement objective
- $L^{VF}$ → [[RL - Key Words|value function]] (square of diff between predicted and actual value → how good it is to be in a certain state)
- $S$ → entropy bonus (to encourage exploration vs exploitation)
- $c_1,c_2$ → coefficients 
- **[[RL Basics|Actor-critic style]]:** 
	- Actor → policy (makes actions based on inputs)
	- Critic → value function (like a coach that evaluates the actor’s performance)

```
for iteration=1, 2, . . . do
	for actor=1, 2, . . . , N do
		Run policy πθold in environment for T timesteps
		Compute advantage estimates Aˆ1, . . . , AˆT
	end for
	Optimize surrogate L with respect to θ, with K epochs and minibatch size M ≤ NT
	θold ← θ
end for
```
- PPO’s strategy:
	- Use the same data for K epochs instead of using it just once 
		- $E_t$ allows us to average results over multiple experiences → reduces noise + randomness

**ALGORITHM:** 
![[Pasted image 20251122215557.png]] 



# References
- https://huggingface.co/blog/deep-rl-ppo
- https://arxiv.org/pdf/1707.06347