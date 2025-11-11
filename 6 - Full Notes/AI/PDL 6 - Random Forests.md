2025-11-09 16:35

Status:


Tags:
[[cs]] 
[[ai]] 
[[ml]] 
[[dl]] 
[[rl]] 


_______
# PDL 6 - Random Forests

*Note* → implemented using [[PDL - Syntax|Scikit Learn]] 

**Binary split:** something that splits rows into two groups (one case where a condition is true, one case where a condition is false)
- I.e. for the [[PDL 3 - NN Titanic Example|titanic example]] → could split by male / female (all males in one branch, all females in another branch)
- *Note* → only need to split, not add in extra information justifying split
- *Note* → can still split continuous variables as well
- Good split = when dependent variable have same value on each side → check with standard deviation
- *Calculating best possible split:* 
	- Go through all possible thresholds (for discrete data) and then calculate the score for each one → find the lowest
- **1R model:** the implementation of this algorithm
	- Is one of the best machine learning classifiers

**Tree:** ensemble of binary splits
- 

**Random forest:** machine learning algorithm used primarily for classification and regression tasks
- Build a collection of decision trees and make predictions based on the [[PDL 5 - Experimenting (Ensembling)|ensemble]] of these trees (reduces overfitting, increases accuracy)
- 





# References

