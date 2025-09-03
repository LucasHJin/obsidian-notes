2025-08-29 16:07

Status:


Tags:
[[ai]] 
[[ml]] 


_______
# PDL - FastAI Sytnax

**`Datablock`**: blueprint for building a dataset
- Main thing you want to be familiar with → how to get data into your model
	- FastAI creates the right model the majority of the time (more technical stuff isn’t that relevant)
- What you pass is all the things that might change between datasets/models 
	- *How to get ready for training* 
- **Parameters:** 
	- `blocks` → inputs and outputs
	- `get_items` → function that returns a list of the items to train the model on
	- `splitter` → function to create a validation set
		- Need to set aside data (not train on it) to test your model afterwards
		- `pct` → how much to set aside
		- `seed` → keeps the validation set the SAME (changes in model aren’t from validation set changing)
	- `get_y` → function that returns the labels for the data (parent folder of each file)
	- `item_tfms` → code that will run on every item in the data set
		- I.e. to resize the images
		- *Note* → batch transforming is faster, run by GPU
- `dataloaders` → class that PyTorch iterates through to grab data
	- Feeds the training algorithm with **batches** of data simultaneously
- [API](https://docs.fast.ai/data.block.html) 

**`learner`**: combines a model (actual neural network) with the training data
- Small [number of neural networks](https://timm.fast.ai/) you pass in that are useful for large number of usecases
	- Most cases → `resnet` family will be fine
- *Note* → FastAI uses **finetuning** instead of training from scratch
	- Pretrained models are fast because they have already been trained to recognize millions of images
	- FastAI → slightly tweaks the weights to fine tune it to a specific dataset

**`DataLoaders:`** similar to datablocks but allows you to use even less code
- Information providing is very similar (i.e. the data, the classification, etc.)

*Note* → label for data is typically in file names or folder path (parent folder)

# References

