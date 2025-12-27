2025-12-25 19:59

Status:


Tags:
[[cs]] 
[[ai]] 
[[rl]] 
[[ml]] 


_______
# RL - Curiosity

Solves these 2 problems:
- *Sparse rewards problem* → most rewards are set to 0 (no information) which makes it harder to progress
	- Happens even if you design the rewards → credit assignment of which actions led to which positive results is hard + you might cause exploitation of rewards
	- Also more realistic to real world scenarios
- *Extrinsic reward system* → human needs to implement reward function for environments (not scalable)

**Curiosity:** intrinsic reward mechanism developed by the agent (will push itself to both explore and learn)
- High reward for new trajectories

**Intrinsic Curiosity Module:** a module that rewards the agent when its internal model of the environment makes large prediction errors (uses curiosity to reward)
- *Module* → core component of an RL system
- **Parts:** 
	- *Feature encoder* → uses feature representation of environment (instead of raw observation space like pixels)
		- Focus on meaningful aspects of env
		- Usually CNN or MLP
		- *Feature representation* → model things that can be controlled / affect the agent
	- *Forward model* → tries to predict what next state looks like given current state + action
		- Calculate curiosity with this
		- ![[Pasted image 20251225225335.png|300]] 
	- *Inverse model* → tries to predict what action lead to this change in state
		- So agent doesn’t learn uncontrollable predictable changes (i.e. random background movement)
		- ![[Pasted image 20251225225326.png|300]] 
- ![[Pasted image 20251225225314.png|400]] 

**Formula:** many different possible calculations
- *Curiosity through next-state prediction*: curiosity is equal to the error in predicting the next state
	- ![[Pasted image 20251225201033.png]] 
	- If it’s unfamiliar → prediction is bad so curiosity is high (make it more likely to explore)
- *Curiosity through random network distillation* 



# References
https://medium.com/data-from-the-trenches/curiosity-driven-learning-through-next-state-prediction-f7f4e2f592fa
