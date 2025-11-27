2025-11-26 23:28

Status:


Tags:
[[cs]] 
[[ai]] 
[[ml]] 
[[dl]] 
[[rl]] 


_______
# PDL 6 - Gradient Boosting

**Boosting:** 
- Like [[PDL 6 - Random Forests]] 
	- Alternative is *bagging* → random forest strategy
- Instead of trees on random subsets of the data 
	- Instead → fit very small trees (minimal splits) and then check **residual** (diff between prediction and actual)
		- Then create small trees to predict residuals of previous trees
	- Take sum of all trees 
- Typically more accurate
	- But might overfit



# References

