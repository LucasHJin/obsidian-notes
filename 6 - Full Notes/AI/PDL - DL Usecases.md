2025-11-02 01:30

Status:


Tags:
[[cs]] 
[[ai]] 
[[ml]] 
[[dl]] 
[[rl]] 


_______
# PDL - DL Usecases

**Computer vision:** 
- Good at object recognition + detection
- Not good at recognizing images with different structure/style to training data
- Can convert non image data into images (i.e. [[CV - PAPER Automated Powerlifting|powerlifting]])
- Challenge → data labelling is very slow 
	- Possible approach → get more data out of limited images with [[PDL - Training a model|data augmentation]] 
**Text (NLP):** 
- Good at generating context driven responses + identifying sentiment, classifying, etc.
- Challenge → no way to verify correctness of info
**Text + images:** 
- Can combine text and images into a single model
- Challenge → same as text (no way to verify)
**Tabular data:** 
- Not great improvements compared to regular algorithms
	- I.e. random forest, gradient boosting
- Increases variety of columns that can be included
	- High cardinality categorical columns (i.e. username → many possible entries)
- Challenge → takes longer to train
**Recommendation systems:** 
- Type of tabular data → good for high cardinality again
- Can combine with additional metadata
- Challenge → basis is more on what the user might like rather than what might be useful
**Other:** 
- I.e. protein chains as text documents
- I.e. sound waves as images

___
**Drivetrain Approach:** method to ensure that your model will be useful
- Steps:
	- What is your objective
	- What actions can you take to meet that objective (levers)
	- What data can you get
	- Build the model that makes the best actions to get best result for objective
		- Levers + uncontrollable variables as inputs
		- Combine outputs to predict final state
- Ex: recommendation systems
	- Objective → drive more sales by recommending things user wouldn’t have otherwise thought of
	- Lever → ranking of the recommendations
	- Data → needed to generate recommendations
	- Model → build 2 models (seeing / not seeing recommendation)
		- Utility function → low value if wouldn’t buy book either way or would buy book either way



# References

