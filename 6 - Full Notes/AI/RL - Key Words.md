2025-10-08 10:58

Status:


Tags:
[[cs]] 
[[ml]] 
[[rl]] 
[[ai]] 


_______
# RL - Key Words

### Optimization Terms
- **Gradient** - The direction and rate of steepest increase for a function. Think of it as arrows pointing uphill on a mountain. In neural networks, we use gradients to know which way to adjust parameters.
- **Objective** - The goal function we're trying to optimize (maximize or minimize). It measures how well our model is doing.
- **Loss** - A function we want to minimize (lower is better). Often the negative of an objective we want to maximize.
- **Parameters (θ)** - The adjustable numbers in a neural network (weights and biases) that we tune during training.
- **Optimization** - The process of adjusting parameters to make the objective better (higher or lower depending on the goal).
### Reinforcement Learning Terms
- **Policy (π)** - A strategy that tells the agent what action to take in each situation. Can be deterministic (always same action) or stochastic (probability distribution over actions).
- **Advantage (Â)** - How much better an action was compared to the average action in that situation. Positive means "better than expected," negative means "worse than expected."
- **Reward (r)** - Immediate feedback the agent gets after taking an action. Like points in a game.
- **Return** - Total accumulated reward over time, often with future rewards discounted.
- **Value Function (V)** - Estimates how good it is to be in a particular state, considering all future rewards from that point.
- **Action** - A choice the agent makes at each step.
- **State** - The current situation or observation the agent sees.
- **Episode** - One complete run through a task from start to finish.
- **Trajectory** - A sequence of states, actions, and rewards over time.
### PPO-Specific Terms
- **Probability Ratio ($r_t$)** - How much more (or less) likely the new policy is to take an action compared to the old policy.
- **Clipping** - Limiting values to stay within a certain range to prevent extreme changes.
- **Epsilon (ε)** - A small threshold value (like 0.2) that controls how much the policy can change in one update.
- **Entropy** - A measure of randomness or exploration in the policy. High entropy means more exploration.
- **Batch** - A collection of experiences used together for one training update (small subset of data used for one gradient update).
	- Number of updates = experiences/batch size
- **Epoch** - one complete pass through all data
	- **Experience:** single piece of data 
- **Timestep (t)** - A single moment in time when the agent observes, acts, and receives reward.

**Logits:** unbounded real numbers that can be turned into probabilities (by applying a softmax function)



# References

