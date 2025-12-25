2025-12-25 01:14

Status:


Tags:
[[cs]] 
[[ai]] 
[[rl]] 
[[ml]] 
[[dl]] 


_______
# DL - Optimizers

**Optimizers:** take the gradients you computed and uses them to update the model’s parameters
- Useful because gradients are typically noisy and poorly scaled → hard to apply the theoretical formula
- Instead, optimizers change the formula:
	- $\theta \leftarrow \theta+\alpha \cdot M(\nabla_{\theta}J)$  
	- Where the function M represents momentum, adaptive scaling, normalization
- *Specific optimizers:* 
	- Stochastic Gradient Descent → default 
	- Momentum → adds memory for smoother gradients (sum up running avg for gradients)
	- RMSProp → normalizes per parameter step size (all parameters move closer to equal amounts)
	- Adam → combines momentum + rmsprop
		- Default for [[RL - Policy Gradient Methods|policy gradient]] 



# References

