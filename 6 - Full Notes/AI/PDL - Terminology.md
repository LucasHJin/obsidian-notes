2025-08-29 22:43

Status:


Tags:
[[ai]] 
[[ml]] 


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
- **Parameters:** weights
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

# References

