2025-10-08 22:23

Status:


Tags:
[[cs]] 
[[ai]] 
[[rl]] 
[[ml]] 


_______
# RL - PAPER Decentralized Control of Quadrotor Swarms

**Key takeaways:** 
- Other techniques like kinodynamic planning or PrSBC have the negative or either constraining movement around them (bad for drone formations) or limit aggressive movement
- Deep Reinforcement Learning → encourage aggressive (reward first) actions while also placing a high emphasis on collision avoidance
	- Policy directly controls motor thrust (continuous action states)
	- No centralized control → use policies that simultaneously / implicitly plan trajectories (assumes no access to global state)

*NOTE:* Quadrotors have motors that spin in 1 direction + generate non-negative thrust
- 4 motors → 0 to 1 thrust

___
**Logic:** 
- $S^{(t)}=(g_{1}^{(t)}, ..., g_{N}^{(t)}, s_{1}^{(t)}, ..., s_{N}^{(t)}$ → state of environment
	- Tuple of goal states of individual drones and current states of individual drones
- $(p, v, R, w)$ → state of individual drone
	- position relative to goal, linear velocity, rotation matrix from drone to global frame, angular velocity
- Learn policy $\pi_\theta(a^{(t)}|o^{(t)})$ 
	- Maps observations to gaussian distribution over continuous actions 
- For knowing neighbour positions
	- Tuple of observations of space and relative positions/velocities
	- Note → only up to N (can be less)

**Reward function:** 3 parts → reward for closeness to target, reward for no collision, auxiliary reward function to facilitate initial stabilizing (penalize high angular velocity, motor thrusts, rotations)

**Embeddings:** let each drone understand itself and its environment in a compact, meaningful way before deciding on an action
- **Drone self embedding:**
	- Encodes drone’s own state into an embedding vector
- **Neighbor embedding:**
	- Deepset encoder → don’t care about order of neighbors or number of neighbors (averages out neighbors)
	- Attention based encoder → create attention weights and focus on most important
		- ==Best performance for target location and collision avoidance== 
		- Prioritizes closer + higher relative velocity vectors (velocity considered over distance (i.e. pointing at drone))
- Policy takes that along with learned scalar parameter (shared across states) → returns action a
___
**Setup:** 
- Randomize orientation, velocities (10x10x10 room, random height from 0.25m to 2m within 3m radius)
- **Scenarios:** 
	- *Static* → Keep fixed target formation (various geometric shapes)
	- *Dynamic* → Change formation origin location + distance between drones
		- *Swarm vs Swarm* → split into 2 and fly through each other
	- *Evader pursuit* → Shared goal (policy) of pursueing some evader
		- 3D Lissajous curve / randomly sampled Bezier curve
___
**Physical deployment:** 
- Neural networks will use 3D space when planning paths to swap goals + more agressive
- Voronoi Cells + PID (traditional) → use a longer path and more in a 2D space
- **Hardware used:** 
	- Crazyflie2.0 → low-power nano-quadrotor platform where on board computation is provided by a microcontroller with 168MHz and 192Kb of RAM
	- Used smaller versions of deep set models → 16 neurons self encoders, 8 neurons neighbor encoders
___
**Conclusion:** successful swarm control can be done with deep reinforcement learning
- Model agnostic → can learn new policies with different parameters by retraining
- No constraints on velocity/acceleration
- Permutation + scale agnostic model architecture → can switch sizes simply

# References
https://arxiv.org/pdf/2109.07735
