2025-10-08 21:51

Status:


Tags:
[[cs]] 
[[uni]] 
[[ml]] 
[[rl]] 


_______
# RL - Custom Environments (Gym)

**Syntax:** 
- `Env` class → implements a simulator that runs the environment to train in
	- `observation_space` → structure + what you can observe about the state
	- `action_space` → numerical structure of valid actions
- **Functions:** 
	- `reset` → resets environment and observation to initial state
	- `step` → takes action as input and transitions to new state
		- Returns observation, reward, done (is it finished), info
	- `env.render(mode = "human")` → allows you to see a snapshot of the environment
- **Spaces:** data structures provided by Gym to describe valid observations and actions
	- `Box(n,)` → n-dimensional continuous space
		- Has a `high` and `low` attribute (boundaries)
	- `Discrete(n)` → discrete space with n possible values (0 to n-1)
- **Wrappers:** allows you to modify environment functionality without making a subclass
	- Also have observation, reward, action specific wrappers


___
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


# References

