2025-08-28 12:36

Status:


Tags:
[[ai]] 
[[ml]] 


_______
# PDL 1 - Getting Started

**How to learn:** 
- Every single lesson has:
	- A video
	- [Kaggle notebooks](https://www.kaggle.com/code/lucashjin/is-it-a-bird-creating-a-model-from-your-own-data/edit) 
	- [Fast AI Chapter](https://github.com/fastai/fastbook?tab=readme-ov-file) 
- Greater focus on building/deploying models (learn as you go)
	- More hands on, less theoretical

*Beforehand*:
- [[PDL - Resources]] 
- [[PDL - Background Info]] 
- [[PDL - Terminology]]

*Notes:* 
- You should view data in between steps just to make sure it’s valid
- You don’t need really big images for computer vision models
- ==Labelling is a very important step and often a big problem== 
	- Need properly processed + structured data

*Learnings:* 
- [[PDL - Computer vision syntax]] 
- **Tabular analysis:** predicting columns from data from spreadsheets/databases
	- Uses [[PDL - Computer vision syntax|tabular data loaders]] → provide very similar data to other cases
	- *Categorical* → can take a few select values
	- *Continuous* → can take any real number
	- Generally → there is no pretrained model
		- So you `fit` models instead of `fine tuning` → need bigger changes
- **Collaborative filtering:** basis for recommendation systems
	- Take data of which users used which products → then find similar users using other products
		- Uses `Data loaders` again
	- *Note* → for the learner, need to pass a range `(below possible min, above possible max)` 
		- Because need to predict how much they would like it (not categories)
- [[PDL - Machine Learning Models]] 
- [[PDL - Neural Networks]]
- Main problems for ML:
	- Do you have enough data
	- Is the data formatted correctly
	- Is the model training correctly

# References

