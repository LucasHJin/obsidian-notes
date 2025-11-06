2025-11-05 22:37

Status:


Tags:
[[cs]] 
[[ai]] 
[[ml]] 
[[dl]] 
[[rl]] 


_______
# PDL - NumPy + PyTorch Vs Python

*Note:* Python is very slow → NumPy and PyTorch (written in C) help speed up computation

**NumPy Array:** multidimensional table of data, with all items of the same type
- **Jagged array:** can have different inner array sizes
- Good at running fast computations on compact structures

**PyTorch Tensor:** same definition as array except with more restrictions
- Tensor MUST BE basic numeric type for all components (can’t be jagged)
- *Note* → this means it can run on GPU
	- Can calculate derivatives



# References

