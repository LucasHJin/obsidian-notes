2025-11-01 17:28

Status:


Tags:
[[cs]] 
[[ai]] 
[[ml]] 
[[dl]] 
[[rl]] 



_______
# PDL - Training a model

**Steps:** 
1. Get data
2. Clean the data
	- *Note* → you **train** the model (i.e. use a [[PDL - Computer vision syntax|Datablock]]) before you **clean** the data
		- Can use the trained model to find out:
			- What things are hard to figure out in your model
			- What are the data problems in your model (better ways to gather data, clean, etc.)
	- Need all images to be same size (data loaders pass batches a few items at a time in the form of a tensor)
		- **Tensor:** a generalization of scalars, vectors, matrices (nth level)
3. Evaluate the model


**Evaluating models:**
- **Confusion matrix** → tells you the category errors you are making (i.e. out of your data how many times is it X but it thinks Y)
	- Only meaningful when labels are categories
	- ![[Screenshot 2025-11-02 at 1.06.18 PM.png|300]] 
- **Plot top losses** → tells you where loss is highest
	- *Bad loss:*
		- Wrong and confident
		- Right and unconfident
	- `ImageClassifierCleaner` → cleans up wrongly labelled data in the dataset
		- Orders by loss (worst first) → if you find incorrectly labelled data, can change label or delete
		- Can clean training/validation data
		- Delete → `for idx in cleaner.delete(): cleaner.fns[idx].unlink()` 
		- Clean → `for idx,cat in cleaner.change(): shutil.move(str(cleaner.fns[idx]), path/cat)` 

**Data augmentation** → when you get multiple images from the same image (allows you to train models on more data from a small dataset)
- I.e. RandomResizedCrop, aug_transforms
- Useful because it allows the model to focus on one specific part of the image → truly recognize the features that make it up
	- I.e. it can start to recognize a paw if it sees it enough and will actually be able to recognize from more angles
- *List:* rotation, flipping, perspective warping, brightness changes, contrast changes

==*Note:* You can save and load models in Kaggle== 
- Can use `load` and `save` to save intermediary models if training takes a long time or if you need to do different training steps → i.e. training a predictor then classifier for [[PDL 4 - Natural Language Processing (NLP)|nlp]] 


# References

