2025-12-26 17:53

Status:


Tags:
[[cs]] 
[[ai]] 
[[rl]] 
[[ml]] 

_______
# RL - Advantage Actor Critic (A2C)

Makes use of [[RL - Actor Critic Methods]] but replaces critic’s action value function with an advantage function
- Stabilizes training

**Advantage function:** how good on average that action is (subtract that state value from that action value) 
- If > 0 → it’s good and push gradient in that direction, else not
- *Note* → use [[RL - Training Strategies|TD error]] to estimate instead of using 2 value functions
	- ![[Pasted image 20251226175613.png|400]] 
		- How good was prediction → estimate using reward gotten + value estimate - current value estimate



# References

