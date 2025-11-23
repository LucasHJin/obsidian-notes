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
	- “2R model” → Can split based off of 1R and then remove the splitter from that and then split based on a second category

**Tree:** (decision tree) ensemble of binary splits
- Combines many binary splits such that you can get stronger predictions at the leaf nodes (based on more specific combinations of categories)
- **Gini:** measure of how mixed the classes are within a dataset or node (impurity)
	- Basically → how often would you be wrong if you randomly guessed class of something in a group (i.e. 1 class = 0, mixed classes = higher)
	- Want to minimize
- **Absolute error:** probability that your class guess (output) is wrong when you guess the most common class

**Random forest:** machine learning algorithm used primarily for classification and regression tasks
- Build a collection of decision trees and make predictions based on the [[PDL 5 - Experimenting (Ensembling)|ensemble]] of these trees (reduces overfitting, increases accuracy)
	- Called **Bagging** (needs uncorrelated + unbiased)
	- Allows you to make decision trees more accurate even if they can’t be trained more specific because of lack of data
- Can create uncorrelated models by training on different random subsets of data (i.e. each on random 50% of data)
- *Note:* 
	- When building decision tree → select random subset of columns for each split (not just random subset of data)
		- Reduces overfitting, reduces amount of choices of columns (i.e. don’t have to check every column for splitting)
	- **Feature importance plot**: Tells you which independent variables were most important
		- How often picked + how much it improved gini
- **Out of bag error:** way of measuring prediction error by using calculation of row’s error trees where the row was not included in the data (i.e. when choosing the subset of data) 
- *Prediction confidence* → can check with standard deviation
	- Smaller = more confident
- **Partial dependence plot:** set everything else equal by setting the independent variable for each row of data and predicting answer and then avg
- 





# References

