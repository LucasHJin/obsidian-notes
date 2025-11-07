2025-11-03 22:57

Status:


Tags:
[[cs]] 
[[ai]] 
[[ml]] 
[[dl]] 
[[rl]] 


_______
# PDL 3 - Neural Net Foundations

**Remember:** [[PDL - Training a model]] 
- Can improve models by using a more proper architecture (i.e. instead of ResNet)
- **[[PDL - Terminology|Architecture]]:** mathematical functions defined by matrix multiplications and non-linearities
	- Care about → how fast, how much memory, how accurate
	- Naming → tells you size of model + if they have been trained on more data
*Note:* using more models
- Need to use `pip install timm` to use most models from PyTorch (FastAI doesn’t have that many)
- *Note* → start off with ResNet18 to be able to try as many things as possible (changing architecture is last step)
	- I.e. start with different data, cleaning data differently, etc.
*Note* → easy to get inputs but not outputs
- I.e. easy to get raw data but not labeled

___
**Learner:** 2 parts
- What you did to turn images into things for the model
- The model itself
	- *Notes:* 
		- Contains many layers (+ nested layers)
		- Each layer is made up of numbers / math functions

___
[[PDL 3 - DL Logic]] 

**Machine learning models:** models that fit functions to data
- I.e. start with a very flexible neural network model and fit it to data to get it to recognize patterns
- **How (DEEP LEARNING):** at a high level, it changes parameters one by one to get the overall function to fit (i.e. quadratic you fit `a, b, c`)
	- **[[PDL - Terminology|Loss function:]]** a function that tells you if the adjustment is getting better or worse
		- `Mean Squared Error = mean((predictions-actuals)^2)` 
			- Can also use `L1 norm` (absolute value of difference)
		- Actuals = data
		- Predictions = what the function would get currently
			- Start with values on either side of 0
		- *Automation* → does loss get better when you move each parameter up/down (use [[PDL - Syntax|derivative]])
			- **Learning rate:** Take out each value and change each value by small value → create a new set of parameters to calculate loss again
				- Example of a [[PDL - Terminology|hyperparameter]] 
				- `w -= gradient(w) * lr` (**stepping** parameters using an **optimizer step**)
			- Don’t change directly by numbers (or else you might overshoot)
		- Repeat this as many times as needed to update parameters
	- **Gradient descent:** calculate gradient and then decrease loss
		- *Optimizers* → built on this principle
	- **Rectified Linear Unit (ReLU):** building block of the math function we want to fit to 
		- Want to create an infinitely [[PDL - Syntax|flexible function]] 
		- Can add together infinite number of ReLU (i.e. each pixel in an image needs its own variable/ReLU)
			- Allows us to have an arbitrarily squiggly function (match with enough ReLUs) 
			- Across infinite *dimensions* as well
		- To get parameters of these ReLUs → use gradient descent
			- Each layer has parameters (linear layer of weights and biases)
			- Then you apply ReLU (non-linear transformation of output of the layer)
			- Then calculate loss based on the ReLU layers to adjust parameters 
		- **Matrix multiplication:** allows us to add together millions of ReLUs
			- ![[Pasted image 20251105111720.png]] 
		- *Note* → just two layers is enough to approximate any function
			- But more layers can help with performance
 - *NOTE:* the optimum point point of a loss function is the minimum (typically looks like a quadratic)
	- THIS IS NOT THE FUNCTION YOU ARE TRYING TO FIT TO THE DATA
	- It’s the loss surface, which represents how good or bad your model’s predictions are for different parameter values

___
[[PDL 3 - NN Titanic Example]] 

**Example:** 
```python
def simple_net(xb): 
    res = xb@w1 + b1
    res = res.max(tensor(0.0))
    res = res@w2 + b2
    return res

w1 = init_params((28*28,30))
b1 = init_params(30)
w2 = init_params((30,1))
b2 = init_params(1)
```
- `w1` → 30 output activations so `w2` → 30 input activations
	- First layer constructs 30 different features representing a mix of pixels (can change amount)


# References

[[PDL - Syntax]] 
[[PDL - NumPy + PyTorch Vs Python]] 