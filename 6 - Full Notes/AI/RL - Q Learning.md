2025-12-19 23:49

Status:


Tags:
[[cs]] 
[[ai]] 
[[rl]] 
[[ml]] 

_______
# RL - Q Learning

**What is it?** 
- An off policy [[RL - Value Based Methods|value-based method]] that uses [[RL - Training Strategies|TD]] approach to train [[RL - Value Based Methods|action-value]] functions
	- **Off policy:** using a different policy for acting (inference) and updating (training)
		- For Q learning:
			- Acting policy → epsilon greedy
			- Updating policy → greedy
	- *Note:* 
		- **On policy** → using the same policy for acting and updating
			- I.e. for “Sarsa” → use epsilon greedy for both
- Q stands for “quality” (value) of action at state
	- Equal to expected cumulative reward

**Q function:** action-value function → determines value of starting at state $s$ and performing action $a$ and then following policy
- ![[Screenshot 2025-12-20 at 5.03.18 PM.png|400]] 

**Q table:** a table where each cell corresponds to a state-action pair value (encodes the Q fxn)
- *Structure:*
	- Columns = actions
	- Rows = number of possible states
		- I.e. for a maze → it would be length * width
- Can search Q table for value of a state + action
	- After training → optimal Q table = optimal policy (highest value action for each state)
___
**Q learning algorithm:** 
- ![[Pasted image 20251220170909.png]] 
- *Simplified steps:* 
	- Initialize Q table with 0
	- Choose an algorithm using [[RL - Epsilon Greedy|Epsilon Greedy]] strategy (handles exploration/exploitation)
		- Decrease epsilon as Q gets better
	- Perform an action and get the resulting reward and state from the action
	- Update $Q(S_{t}, A_{t})$ by using bootstrapping → immediate reward + discounted value of next state (action that maximizes Q guess at the next state)
		- ![[Pasted image 20251220171613.png]] 
		- To get the best action state pair value of the next state → just take the max (greedy)
		- Then start in new state and choose new action (repeat)
	- *Note*:
		- First couple steps before repeat are to set the epsilon and step counters, and to initialize the episode by getting initial state observation




# References

