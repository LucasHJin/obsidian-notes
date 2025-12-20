2025-12-20 00:06

Status:


Tags:
[[cs]] 
[[ai]] 
[[rl]] 
[[ml]] 


_______
# RL - Value Based Methods

**Value function:** function that maps a state to the expected value of being at that state

**Finding optimal policy:** 
- In *policy based methods* → policy is found through training
	- I.e. train the model to choose an action based on current state
		- You don’t have a value function
- In *value based methods* → policy needs to be specified manually (not trained)
	- I.e. just a pre defined function to select an action based off of values from value-function
	- *Note* → finding optimal value function leads to optimal policy
		- Often use Epsilon-Greedy Policy
	- ![[Screenshot 2025-12-20 at 12.10.13 AM.png|300]] 

Remember → [[RL - Deep RL Basics]] 
- **2 types of value based functions**
	- *State value:* 
		- ![[Screenshot 2025-12-20 at 12.11.46 AM.png|400]] 
	- *Action value:* 
		- ![[Screenshot 2025-12-20 at 12.12.31 AM.png|400]] 
		- I.e. if you had 4 directions then there are 4 possible actions per state
 
**Bellman Equation:** simplifies calculation for value based functions (i.e. finding total reward by calculating and adding up all values)
- Similar to [[Dynamic programming explained]] (recursive function)
- ![[Screenshot 2025-12-20 at 12.34.04 AM.png]] 
	- Instead of calculating each value as the sum of expected return (only consider following reward + value of following state)
	- Can call the next function to find partial value and so on


# References

