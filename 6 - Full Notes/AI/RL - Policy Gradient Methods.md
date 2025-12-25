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

**Gradient Ascent:** gives the direction of steepest increase of J (locally) → which direction should you go to make slope more steep
- *Update step:* $\theta \leftarrow \theta+\alpha \cdot \nabla_{\theta}J(\theta)$ 
	- New parameters = old parameters + small step in the upwards direction
		- Magnitude + direction governed by nabla J
	- *Note* → $\nabla$ represents vector of partial derivatives (forms a gradient vector)
	- Implemented practically with [[DL - Optimizers|optimizer]]
- *Note* → GD = minimize, GA = maximize
	- So GD → change the + to a -
- **Problems:** 
	- Calculating gradient of objective is computationally expensive → calculate gradient estimation with sample trajectories (instead of all)
	- State distribution is sometimes unknown (can’t differentiate then)
		- Use **Policy gradient theorem:** 
		- ![[Screenshot 2025-12-24 at 5.05.02 PM.png]] 
	- **Baseline:** value you subtract form the return R(t)
		- Helps normalize extreme value + center around 0 (this is what DL expects)

**Reinforce algorithm (Monte Carlo Reinforce):** policy-gradient algorithm that uses an estimated return from an entire episode to update the policy parameter $\theta$ 
- Logic:
	- Collect an episode $\tau$ with policy $\pi_{theta}$ 
	- Use the episode to estimate gradient:
		- ![[Pasted image 20251224170838.png|500]] 
		- $\log A$ → tells you how to change weights to increase/decrease probability of choosing action a at state s
		- $R$ → increases / decreases probability of the chosen state action combinations based on good / bad
			- I.e. if it had a negative reward → the direction of log A gets reversed so it’s less likely
	- Update weights
- *Note* → can calculate multiple trajectories:
	- ![[Pasted image 20251224171542.png]] 
	- Just average out all trajectory estimations

**Reward to go PG:** 
- [Source](https://spinningup.openai.com/en/latest/spinningup/rl_intro3.html#don-t-let-the-past-distract-you) 
- When calculating return, only calculate from time $t$ onwards (instead of 0)
	- Because action $a_t$ only influences rewards after time $t$, not before
	- ![[Screenshot 2025-12-24 at 11.08.36 PM.png]] 

**Syntax:** 
```python
policy_loss = torch.cat(policy_loss).sum() #concatenates into 1 tensor and sums up total loss

# stop previous episode gradients from stacking
optimizer.zero_grad()
# calculate gradient for policy los
policy_loss.backward()
# update policy parameters
optimizer.step()

```

# References

