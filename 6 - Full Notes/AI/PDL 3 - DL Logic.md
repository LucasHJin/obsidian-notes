2025-11-05 22:59

Status:


Tags:
[[cs]] 
[[ai]] 
[[ml]] 
[[dl]] 
[[rl]] 



_______
# PDL 3 - DL Logic

**Deep Learning Basic Logic:** 
1. Initialize the weights.
	1. Random values
2. For each image, use these weights to predict whether it appears to be a 3 or a 7.
3. Based on these predictions, calculate how good the model is (its loss).
	1. Bad = bigger loss
4. Calculate the gradient, which measures for each weight, how changing that weight would change the loss
	1. If you change weight, does loss go up/down (**gradients**)
5. Step (that is, change) all the weights based on that calculation.
6. Go back to the step 2, and repeat the process.
	1. Optimization looks like reaching the minimum of a quadratic (pick a random point on it and optimize)
	2. **Mini-batch (batch size):** bigger batch = more accurate but longer time and less batches per epoch (use [[PDL - Syntax|data loader]])
7. Iterate until you decide to stop the training process (for instance, because the model is good enough or you don't want to wait any longer).
	1. How many epochs
![[Screenshot 2025-11-05 at 10.59.51 PM.png]] 


# References

