2025-11-08 20:21

Status:


Tags:
[[cs]] 
[[ai]] 
[[ml]] 
[[dl]] 
[[rl]] 


_______
# PDL 5 - From-scratch Models

**To know:** 
- [[PDL - Terminology]] 
- [[PDL 3 - Neural Net Foundations]] 
- [[PDL 3 - DL Logic]] 
- [[PDL - Syntax]] 

*Note* → ==you should know frameworks, not from scratch== 
- Waste of time to look at specifics and tuning all the variables/constants
- Can do as much feature engineering as desired
	- **Feature Engineering:** process of creating, transforming, or selecting variables (features) from raw data to improve the performance of a machine learning model
		- I.e. can create new features, transform (normalize), convert categorical to numerical, choose features, etc.

[[PDL 5 - Experimenting (Ensembling)]]
___
### Data cleaning/preprocessing - Feature Engineering
**Replacing missing numbers:** 
- *Note* → never just delete data (may be important)
- *Strategies:* 
	- Impute (replace) all missing values with the mode of every column
	- Replace with median (better against outliers)
	- Replace with mean
	- Autoencoder → train an autoencoder to reconstruct inputs based on learned representations

**Normalizing data:** 
- Can take log → remove any very big outliers
	- Good for things that grow exponentially (i.e. money)
- Divide by max for each column
- Subtract mean and divide by standard deviation

**Dummy variables:** Binary columns created to represent categorical data numerically
- I.e. if you have `color: red, blue, yellow` → creates a 0/1 column for red, blue and yellow (can drop yellow if wanted)
- *Note* → can’t apply this to distinct columns (i.e. names)
	- But you can make algorithms for these columns

___
### PyTorch Data Processing
**Tensors** → need for [[PDL 3 - Neural Net Foundations|matrix multiplication]]
- *Dependent* → what you are trying to predict (the label/category)
- *Independent* → all the data you are trying to use to predict
	- *Note* → needs to be float (or long) for matrix multiplication
- RECALL [[PDL - Terminology|RANK AND SHAPE]] 
	- For MM → the inner dimension must match (i.e. number of columns)

*Note* → if you don’t set a random seed, each time you train it will be slightly different (good for experimenting)

**Broadcasting rules**:
- *General* → works as long as the last index of each tensor is same size
	- Also → needs to align from the right and each dimension must be either equal or 1

**Steps:** 
1. Create random coefficients for each column
2. Multiply independent tensor by the random coefficients and add up over the columns
	1. RECALL → **broadcasting:** where you apply each of the vector values to each of the rows in the matrix (*element-wise*)
	2. Gives us predictions (our first predictions that we can optimize on - one per column)
3. Use gradient descent to improve these coefficients
	1. [[PDL - Terminology|Loss function]]→ mean of absolute value of difference
	2. Want derivatives for the coefficients → when calculating loss, is saves the function to backwards
	3. Subtract gradient times learning rate from coefficients
	4. REPEAT
4. Metrics:
	1. Accuracy → if >0.5 then survived (Take mean of that tensor)

___
### More Notes (Optimizations) 

**Sigmoid:** a function that keeps values between 0 and 1
- ![[Pasted image 20251109150412.png|500]] 
- Most values are very near to 0/1 because of its horizontal asymptotes 
- Makes it much easier to optimize (easier to see how well the model works)
	- So it's easier to tune hyperparameters

___
### Neural Net - SCRATCH

[[PDL - Terminology|NEED TO KNOW:]] 
- **Hidden layer:** set of neurons between input and output (has parameters)
- **Activations:** values/output of the neurons that get sent as inputs to the next hidden layer
	- *Note* → need to apply an activation function like ReLU first

**Replacing with matrix multiplication:** 
- Replace `(t_indep*coeffs).sum(axis=1)` with `indeps@coeffs` 
	- Also need to create a rank 2 tensor instead of rank 1 for coeffs
		- `1` in the second column for all
	- Then need to turn dependent variable into rank 2 as well
	- *Trailing unit axis* → X rows, 1 column
	- Add on constant each time (so that even if all features are 0, prediction ≠ 0)
- **Reason:** allows you to expand + create a neural network
	- I.e. can create 2 layers
	- First layer → `n_hidden` activations/values per row (each corresponds to a linear graph)
		- `n` hidden neurons 
	- Second layer → need to multiply each of those 20 values by a value to get predict (1 value to predict survival for instance)
		- `layer1 = (torch.rand(n_coeff, n_hidden)-0.5)/n_hidden` 
		- `layer2 = torch.rand(n_hidden, 1)-0.3` 
```python
model = nn.Sequential(
    nn.Linear(n_coeff, n_hidden),
    nn.Linear(n_hidden, 1)
) # same as this
```
- *Note* → also need a constant term (for `b`) 
	- Can just create a scalar random number

___
### Deep Learning





# References

