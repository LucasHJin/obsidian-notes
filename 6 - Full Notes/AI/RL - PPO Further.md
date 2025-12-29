2025-12-28 14:37

Status:


Tags:
[[cs]] 
[[ai]] 
[[rl]] 
[[ml]] 


_______
# RL - PPO Further

**Continuous:** 
- In discrete spaces → convert logits into probabilities using a softmax
- In continuous spaces → policy outputs parameters for normal distribution to represent actions in continuous space
	- Represented as a [[Normal distribution explained|normal distribution]] 
	- Mean $\mu$ → given by actor network (policy)
	- Standard deviation $\sigma$ → fixed or learned
		- Controls exploration (how spread out distribution is) 

**Optimizations:** 
- *Generalized Advantage Estimatino (GAE-Lambda):* 
	- Allows you to fine tune [[RL - Bias vs Variance Tradeoff|bias-variance]] tradeoff in calculating advantage estimate
		- Uses a parameter to control influence of future advantages
	- Remember:
		- TD = Reward + (Discount Factor * Value of Next State) — Value of Current State
		- ![[Screenshot 2025-12-28 at 9.04.32 PM.png]] 
			- γ is discount factor
			- λ is parameter controlling bias-variance
		- *NOTE* → td error ≠ advantage (it is used to estimate td error alongside other factors)
- *Advantage Normalization:* 
	- Advantage scale can change a lot between episodes
		- If it’s too big, clipping doesn’t work because both values will be multiplied by advantage and be too large
	- ![[Screenshot 2025-12-28 at 9.07.58 PM.png]] 
		- Epsilon is small constant for stability
		- Mean + std
- *Gradient Clipping:* 
	- *NOTE* → this is not policy clipping (this clips the gradient updates from the loss)
		- Second safety net to prevent too big updates
	- Clip gradients after backpropogation
- *Value Function Clipping:* 
	- Stabilizes critic (prevents it from changing too much per update)
		- This stabilizes advantage estimates as well
	- Instead of MSE → ![[Screenshot 2025-12-28 at 9.14.12 PM.png|450]] 
- *Learning Rate Annealing:* 
	- Decreases learning rate with time
	- Allows for more learning at the start and then a more stable convergence later on (won’t unlearn later on)
		- $a_{t}=a_{0}(1-\frac{t}{T})$ 
- *Observation Normalization:* 
	- Gets rid of units so that everything is the same scale (provides smoother gradients)
	- $obs_{norm} = (obs − μ) / σ$ 
- *Action Rescaling:* 
	- Need to sometimes bound policy outputs in continuous spaces
	- I.e. if actions can only be from -1 to 1
		- Use tanh to get a range of -1 to 1 and then multiply by scale if necessary + bias
- *KL Stopping:* 
	- *KL Divergence* → how much the new policy changed from the old policy
	- We track it because clipping might not be enough and policy might be updated too much still
	- ![[Screenshot 2025-12-28 at 11.54.46 PM.png]] 
		- If stopped → break out of this current batch SGD updating and perform a new rollout with new data
		- *Note* → don’t save policy
		- ![[Screenshot 2025-12-28 at 11.56.25 PM.png]] 



# References

