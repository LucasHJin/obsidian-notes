2025-12-25 10:32

Status:


Tags:
[[cs]] 
[[ai]] 
[[rl]] 
[[ml]] 
[[dl]] 


_______
# DL - Activation Functions

**Activation functions:** Functions applied to a model’s raw outputs (logits) to introduce non-linearity or to map values into useful ranges

**Specifics:** 
- *Softmax* → takes vector of real numbers and turns into probability distribution
	- *Note* → temperature controls how much exploration vs exploitation (1 is normal)
	- For discrete action policies
- *Sigmoid* → creates 1 probability 
	- For binary actions (Bernoulli probability)
- *Tanh* → outputs continuous range of (-1, 1)
	- For continuous action policies
- *[[PDL 3 - Neural Net Foundations|ReLU]]* → creates non linear patterns (all values ≥ 0)
	- *Leaky ReLU* → allows negative values but makes them smaller (fixes dying ReLU problem)
	- Dying ReLU → if it always outputs 0, it may stop learning





# References

