2025-08-29 22:43

Status:


Tags:
[[cs]] 
[[ai]] 
[[ml]] 
[[dl]] 
[[rl]] 

_______
# PDL - Terminology

**Classification vs Regression:** two main types of ML models
- Classification → predicts a class/category (discrete possibilitites)
- Regression → predicts 1+ numeric quantities (i.e. temperature, location)
	- *Note* → NOT RELATED TO LINEAR REGRESSION

**Overfitting:** when the model starts memorizing the training data instead of generalizing observations/characteristics
- ![[Screenshot 2025-08-30 at 1.41.04 PM.png|350]] 
- **Hyperparameters:** higher level choices that govern the meaning of weight parameters
	- I.e. network architecture, learning rates, data augmentation strategies, etc.

**Transfer learning:** using a pretrained model for another purpose
- Much quicker → replaces last/last couple of layers to specify to new use case
- **Head:** new layers that replace the last later part of model (which were more tuned to specific use case)
- **Inference:** ability of AI models to predict info from data they haven’t seen before (unrelated)

**Test set:** even more exclusive set of data used to evaluate (NOT IMPROVE) the model (hide from even self)
- Training data → model is fully exposed to this data
- Validation data → model is partially exposed to this data (from hyperparameters)
	- Allow us to make decisions on adjusting hyperparameters
	- Evaluates the model during training (avoid overfitting)
- *Note* → validation and training sets should be representative of the entire dataset
	- Not just random picked most of the time

**Convolutional Neural Network (CNN):** type of neural network specifically good for [[PDL - Computer vision syntax|computer vision]] tasks

Relates to [[PDL - Machine Learning Models]] 
- **Architecture:** the functional form of the **model** - template or structure of the model we are trying to fit
	- I.e. `resnet34` → 34 layers
	- **Layers:** the amount of training it goes through each epoch
		- Less epochs before overfitting but more accurate on higher data
	- **Epoch:** how many passes through data set
- **Parameters:** weights + biases (wx+b)
- **Independent variables:** data that doesn’t include the labels
	- Can calculate **predictions** from this (the **results** of the model)
- **Loss:** measure of how well the model **performed** (depends on **predictions** + **labels**)
- **Labels:** also known as **targets/dependent variables** → the desired results
	- I.e. “cat” or “dog”
- **Metric:** function that tells you the quality of the model’s predictions using the validation set
	- I.e. `accuracy = 1 - error rate` 
	- *NOTE* → this is different from loss
		- Loss is optimized for changing weights with stochastic gradient descent (not for human understanding)
- **Fine tuning:** where the parameters of a pretrained model are updated by training for additional epochs using a different task
	- Not complete restart
	- **Fit:** update parameters of a model to make it predict labels better

![[Screenshot 2025-08-29 at 10.46.29 PM.png]] 

___
### Neural Networks

**Baseline:** a simple model that should perform reasonably well (allows you to check against your actual iterated models)

**Tensor:** essentially a multi-dimensional array
- **Shape** → tells you length of each axis (how many values in each)
	- *NOTE* → the assigned values are decided by the user, not by PyTorch
- **Rank** → number of axes/dimensions

**Activation function (linearity):** a math operation applied to a neuron’s output to determine if it sends information and how strongly to the next layer
- Introduces non-linearity when adding the layers
- I.e. ReLU, Sigmoid
	- **ReLU** → Function that returns 0 for negative numbers and doesn't change positive numbers 

**Activation:** Numbers that are calculated (both by linear and nonlinear layers)
**Parameters:** Numbers that are randomly initialized, and optimized (that is, the numbers that define the model)

**Layers:** all things in the Neural Network
- Linear layers → the linear lines

**Forward pass:** Applying the model to some input and computing the predictions
**Backward pass:** Computing the gradients of the loss with respect to all model parameters

**Loss:** A value that represents how well (or badly) our model is doing
**Gradient:** The derivative of the loss with respect to some parameter of the model
**Gradient Descent:** Taking a step in the directions opposite to the gradients to make the model parameters a little bit better
- Multiply by learning rate


# References

