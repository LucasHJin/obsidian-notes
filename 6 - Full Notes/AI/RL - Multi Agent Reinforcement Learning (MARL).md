2025-12-26 20:13

Status:


Tags:
[[cs]] 
[[ai]] 
[[rl]] 
[[ml]] 



_______
# RL - Multi Agent Reinforcement Learning (MARL)

**Multi agent environments:** 
- *Cooperative* → agents working together to maximize a common benefit
- *Competitive/Adversarial* → agents maximize individual benefit by minimizing opponent’s
- *Mix* → agents on the same team but also competing against others
	- I.e. 2v2 soccer

___
### Designing MARL systems
**Decentralized system:** 
- Train each agent independent from one another (i.e. each learns it’s own policy, has it’s own state, action, etc.)
	- ![[Pasted image 20251226212735.png]] 
	- Benefit → simplicity (agent considers other agents as part of the environment dynamics)
	- Negatives → makes environment non stationary
		- Harder to reach a global optimum
		- Also might fail if desired global state ≠ local state

**Centralized system:** 
- Use an experience buffer to collect all agent experiences and train a shared policy on that
	- ![[Pasted image 20251226212918.png]] 
	- I.e. if you have multiple robots trying clean a room, you could have a shared observation of coverage map + current location
	- Use these observations to create a policy to move all robots optimally
		- This makes it stationary → env dynamics doesn’t depend on other agents + shared policy


# References

