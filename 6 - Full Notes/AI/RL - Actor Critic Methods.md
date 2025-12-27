2025-12-26 07:56

Status:


Tags:
[[cs]] 
[[ai]] 
[[rl]] 
[[ml]] 


_______
# RL - Actor Critic Methods

**Actor Critic methods:** hybrid architecture combining value-based and Policy-Based methods that helps to stabilize the training by reducing the variance
- *Actor* → controls agent behaviour ([[RL - Policy Based Methods]]) 
	- $\pi_{\theta}(s)$ 
- *Critic* → measures how good a taken action is / provides feedback ([[RL - Value Based Methods]])
	- $\hat{q}_{w}(s,a)$ 
	- Also updates it’s own method of providing feedback

**Solves this [[RL - Reinforce Algorithm|reinforce]] problem:** 
- Return is calculated with Monte Carlo sampling which has a lot of [[RL - Bias vs Variance Tradeoff|variance]]
	- (Tradeoff for being unbiased because you’re not estimating)
	- Possible solution is to use more trajectories to have a better average out for each trajectory → but it reduces sample efficiency (need a lot of samples, each one contributes less to learning)

___
**Process:** 
- Get current state $S_t$ and pass to Actor + Critic
- Policy → take state and output action $A_t$ 
- Critic → take action + state ($A_t, S_t$) and compute Q value of that state-action pair
- Perform action → output new state $S_{t+1}$ and reward $R_{t+1}$ 
- Update actor’s policy parameter with Q value
	-  ![[Screenshot 2025-12-26 at 5.50.50 PM.png]] 
	- Use new policy to output new action $A_{t+1}$ from new state $S_{t+1}$ 
- Update critic’s value parameters
	- ![[Pasted image 20251226175134.png]] 


# References

