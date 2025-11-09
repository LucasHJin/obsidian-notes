2025-11-08 01:13

Status:


Tags:
[[cs]] 
[[ai]] 
[[ml]] 
[[dl]] 
[[rl]] 



_______
# PDL 4 - Overfitting

> One of the main problems of machine learning
- It’s why having separate training, validation, testing sets are necessary

**Underfitting** → when the model isn’t complex enough to fit the given data
- I.e. if it’s just a straight line → just systematically incorrect/biased

**Overfitting** → when the model fits to the exact given data point but wouldn’t be able to predict properly external data
- Harder to recognize (data fits well)
- **Solution:** remove part of the original data set and then fit the model using the new data → measure by looking at only the removed points (separate [[PDL - Terminology|training / validation sets]])

**Creating a GOOD validation set:** 
- Can’t just pick random data (want an accurate representation of the overall data)
- Depends on what you are trying to predict
	- I.e. might take latter half of data if you are trying to predict future trends
- *Note* → cross validation ≠ validation set

**Metrics:** the data you measure on validation set
- *Note* → [[PDL - Training a model|loss]] ≠ metric
- There isn’t 1 metric that tells you whether it’s good or bad
	- Need to determine carefully + can check multiple metrics (easier for simple models)

# References

