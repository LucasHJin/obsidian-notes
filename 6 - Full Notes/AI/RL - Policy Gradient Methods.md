2025-12-23 14:45

Status:


Tags:
[[cs]] 
[[ai]] 
[[rl]] 
[[ml]] 
[[dl]] 


_______
# RL - Policy Gradient Methods

**Definition:** methods where you optimize policy directly by directly changing parameters $\theta$ with gradient ascent on the objective function

**Advantages:** 
- Simpler → can estimate policy without storing additional value data
- Stochastic policy → can output probabilities ([[RL - Value Based Methods|value functions]] can’t)
	- Automatic exploration/exploitation → not same path every time
	- Gets right of **perpetual aliasing:** when 2 states seem same but need different actions
		- ![[Pasted image 20251223144838.png|400]] 
		- *Deterministic policy* → will always fail
		- *Quasi deterministic policy (value)* → will spend a lot of time before success
		- *Optimal stochastic policy* → will move randomly L / R so higher chance of success
- Better for larger action spaces → because for value, you will need a value for every possible action
	- Hard for continuous actions
- Better convergence properties → less deterministic so when probabilties change by small amounts, the actual change in chosen actions isn’t large
	- In value functions → max is very harsh
		- I.e. if it goes from 0.21<0.22 to 0.23>0.22, you will always choose this action from never

**Disadvantages:** 
- Might converge to local max instead of global
- It is slower
- Can have higher variance

____
**Specifics:**  
- Let an agent interact during an episode
	- Get back the return
	- Increase the probability of each (state, action) pair if good return, else decrease
- **Stochastic policy:** 
	- ![[Screenshot 2025-12-23 at 3.27.23 PM.png|400]] 
		- $\pi_{\theta}(a_{t} | s_{t})$ is probability of choosing action at from state st
- Use **objective function** $J$ to determine if policy is good (cumulative expected reward)
	- Want to find weights $\theta$ that maximize J
	- ![[Screenshot 2025-12-23 at 3.28.44 PM.png|400]] 
	- **Trajectory:** state action sequence without considering reward
		- Related to episode
	- *Cumulative expected reward* → sum of probability of trajectories times the expected reward from those trajectories
		- ![[Screenshot 2025-12-23 at 5.17.07 PM.png|400]] 
			- *Note* → probability of a trajectory is dependent on $\theta$ which defines the policy choosing states + actions of a trajectory
			- ![[Screenshot 2025-12-23 at 5.18.42 PM.png|400]] 
				- *Note* → inner P is environment transition probability (how likely is it to transition to state $s_{t1}$ given $s_t$ and $a_t$)
				- In a stochastic environment → might not always be 100% (i.e. might slip in frozen lake)

**Gradient Ascent:** 
- 

# References

