2025-11-04 00:59

Status:


Tags:
[[cs]] 
[[ai]] 
[[ml]] 
[[dl]] 
[[rl]] 


_______
# PDL - Syntax

**FastAI:** 
- [[PDL - Computer vision syntax]] 
- `learn.dls.vocab` → list of categories
- It is very good at building models from spreadsheets

**Pytorch:** 
- `stack` → can stack up individual tensors into a single tensor (rank-n+1 tensors)
	- Will often convert to float (and divide to normalize between 0-1)
	- `shape` → length of axis
	- `ndim` → rank (how many axes)
- **Calculating derivative:** 
	- Make a function that takes coefficients of a quadratic and returns its loss (mse)
	- Put all parameters in a single 1D (rank 1) tensor → `params.requires_grad()` 
		- Any calculations need gradient to be calculated
	- `loss.backward()` → calculates gradient (adds `.grad`) to the loss
		- Gives you a tensor for each parameter → tells you how much loss will go down/up if you increase each param
		- **Back propogation** 
	- `with torch.nograd()` → standard neural net deep learning model inner loop
		- Do it without gradient to calculate new gradient
- **Infinite flexible function:** 
	- ![[Screenshot 2025-11-05 at 10.54.36 AM.png|300]] 
		- `torch.clip` → makes negative things 0
	- ![[Screenshot 2025-11-05 at 10.57.28 AM.png]] 
		- Can add together infinite ReLUs
- `array()` / `tensor()` → creates arrays/tensors by passing lists (or lists of lists)
	- Uses `,` to go to nested indices instead of more square brackets
	- `view` → changes shape without changing content (-1 means make the axis as big as needed to fit the data)
	- `where` → works like list comprehension (distance from 1 if should be 1, from 0 if should be 0, etc.)
	- `sigmoid` → guarantees values between 0 and 1
	- `.grad.zero_()` → need to set gradient to zero so it doesn’t add on to previous values
- **Broadcasting:** automatically expand the tensor with the smaller rank to have the same size as the one with the larger rank
	- I.e. `big tensor - small tensor` → expands small one by repeating values
	- *Note* → no extra memory allocation + done in C
	- **Elementwise** 
- *Note* → PyTorch has dataloaders as well (shuffles before batching)
	- `DataLoader` → take any Python collection and turn it into an iterator over mini-batches
	- `Dataset` → a collection that contains tuples of independent and dependent variables is known in PyTorch
		- Pass DS to DL → get back mini-batches which are themselves tuples of tensors representing batches of independent and dependent variables

**Python / Jupyter Notebook:** 
- List comprehension → method of iterating through a list to apply a function to each value
	- I.e. `seven_tensors = [tensor(Image.open(o)) for o in sevens]` → makes a list of tensors for each image in sevens
- `partial` → use to fix some parameters
- `np, normal` → to make random data
	- `linspace` → creates tensor of data points
- `@interact()` → allows you to change values to modify in real time 



# References

