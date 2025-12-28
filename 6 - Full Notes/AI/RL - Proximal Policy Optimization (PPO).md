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
- *Essentially:* 
	- [[RL - Actor Critic Methods|Actor-critic algorithm]] where updates are clipped so that new policies aren’t too far away from old ones

**Reasoning:** 
- Smaller policies are more likely to converge to optimal solution
- Too big policies can lead to bad policies (make it harder to revert)
- ![[Pasted image 20251006215856.png|200]] 

**Problem with [[RL - Reinforce Algorithm|Reinforce]]:** 
- Step size → either too slow or too much variation
- **Clipped surrogate objective function** → new objective function that constrains policy change to a small range
	-  ![[Screenshot 2025-10-08 at 11.02.59 AM.png]]
		- $L^{CLIP}$ → Loss/objective function to be maximized
		- $E_t$ → empirical average over a batch of samples of timestamp t
		- **Unclipped part:** 
			- $r_t$ (ratio) → probability of taking a certain action at a certain state for current and previous policy (estimate how much of a change)
				- ![[Screenshot 2025-12-27 at 10.52.13 AM.png|200]] 
				- Replaces log part of Reinforce
		- **Clipped part:** 
			- $\text{clip}(r_t(\theta),1-\epsilon,1+\epsilon)$ –> restricts the ratio to within a certain range (no large policy updates)
				- *Note* → this is 1 of 2 strategies 
				- The other is TRPO (complicated)
				- $\epsilon$ hyperparameter
		- $A_t$ ([[RL - Advantage Actor Critic (A2C)|advantage]]) → tells us if the action was better or worse than average
			- Acts as the reward in the update
- **When to update policy:** 
	- If ratio is in the range $[1-\epsilon, 1+\epsilon]$ 
	- *Note* → if A>0 (good action) then PPO clips upwards
		- Make sure update isn’t too big but don’t artifically make good action less likely (let it learn)
	- *Note* → if A<0 (bad action) then PPO clips downwards
	- ![[Pasted image 20251227110457.png]]
	- *Note:* 
		- **Gradient:** direction of change
		- **Advantage:** magnitude + sign of feedback
			- IF A>0 → GUARANTEED INCREASE
	- ==ALWAYS WANT TO APPROACH THE RANGE, CENTERING AROUND 0== 

**Algorithm:** 
![[Screenshot 2025-12-27 at 11.11.21 AM.png]]
- $L^{CLIP}$ → clipped policy improvement objective
- $L^{VF}$ → [[RL - Key Words|value function]] (square of diff between predicted and actual value → how good it is to be in a certain state)
- $S$ → entropy bonus (to encourage exploration vs exploitation)
- $c_1,c_2$ → coefficients 
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
- *NOTE:* 
	- Clipped surrogate + entropy → actor loss function
	- Squared error value → critic loss function
	- You add them together into 1 loss because pytorch automatically backpropogates to update both individually simultaneously 

**ALGORITHM:** 
![[Pasted image 20251122215557.png]] 



# References
- https://huggingface.co/blog/deep-rl-ppo
- https://arxiv.org/pdf/1707.06347