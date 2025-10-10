2025-10-08 21:51

Status:


Tags:
[[cs]] 
[[uni]] 
[[ml]] 
[[rl]] 


_______
# RL - Custom Environments (Gym)

https://gymnasium.farama.org/introduction/create_custom_env/
- Inherit from `gymnasium.Env` 
	- Define observation + input spaces
- Observations → need a function to translate internal environment state to obs format
- Reset function → start a new episode
	- Take seed (reproducible randomness) and options (additional configs)
- Step function → core logic
	- Take action, update environment state, return results

http://arxiv.org/pdf/1606.01540
- **OpenAI Gym** → collection of environments to help benchmark tasks/models
	- Abstracts only environment → so user can make online learning/batch update agents
	- Measure performance based on *final performance AND sample complexity (how long it took to train)* 
	- 


# References

