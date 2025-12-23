2025-12-21 00:32

Status:


Tags:
[[cs]] 
[[ai]] 
[[rl]] 
[[ml]] 


_______
# RL - Deep Q Learning

Inspired by [[RL - Q Learning]] 
- But uses [[PDL - Neural Networks|neural network]] instead of a Q table to take a state and approximate a Q value for each action from that state

**Differences:** 
- In Q Learning → you input state + action and get a returned Q-value
- In Deep Q Learning → you input only state and get a returned vector of possible Q-values for all possible actions at that state

___
**Deep Q-Network:** 
- ![[Pasted image 20251222011646.png|400]] 
	- For Atari specifically
- *Notes:* 
	- Need to preprocess input to reduce state complexity 
		- I.e. can reduce state space (size) and grayscale → reduces color channel from 3 to 1 + crops
	- Stack frames together to handle ==temporal illusions== 
		- Allows model to recognize movement
	- Use [[DL - CNN explained|convolutional layers]] to capture spatial relationships
	- Use fully connected layers to output a Q value for each possible action
		- *Note* → they combine all learned features to make a final decision
		- Just a standard [[PDL - Terminology|dense layer]] 

**Deep Q Algorithm:** 
- Similar to Q Learning Algorithm
- Just change the updating step:
	- Create a loss function that compares our Q-value prediction and the Q-target and uses gradient descent to update the weights of our Deep Q-Network
	- ![[Pasted image 20251222105111.png]] 
- Training has 2 phases:
	- *Sampling* → perform actions and store observed experience tuples in a replay buffer
		- Just getting data
	- *Training* → choose batches of these tuples to learn using [[PDL - Terminology|gradient descent update]] 
		- Actually learning from data
	- ![[Pasted image 20251222105521.png|600]] 

**Stabilizing training:** or else training won’t improve properly
- *Experience replay* → store experiences in replay buffer to be reused in training multiple times (often represented as numpy array)
	- Choose random mini-batches of tuples (state, action, reward, done)
	- Reduces correlation between experiences (NN expects independent data) + avoids catastrophic forgetting
		- **Catastrophic forgetting:** Only remembering more recent data
	- ![[Pasted image 20251222111033.png]] 
		- N is a hyperparameter
	- *NOTE* → this does not remove temporal learning
		- Experience is one transition from state $t$ to $t_1$ 
			- BUT → a single state can have multiple stacked states
- *Fixed Q Target* → solves weight correlation between TD target and Q value when calculating loss
	- Leads to significant oscillation (because when you update the network, both values change)
	- **Solution** → use different network with fixed parameters for TD target
		- Update fixed parameters with Q network every C steps
	- ![[Pasted image 20251222111336.png]] 
- *Double DQN* → solves problem of overestimating Q values
	- At the beginning → picking max Q value isn’t necessarily accurate
		- Because it depends on the actions we tried + states explored
	- **Solution** → use 2 networks to evaluate WHICH + HOW GOOD
		- *DQN network* → which action is best (highest Q value)
		- *Target network* → how good is action (actual score)



# References

 