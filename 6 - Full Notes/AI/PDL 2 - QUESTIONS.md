2025-11-02 13:41

Status:


Tags:
[[cs]] 
[[ai]] 
[[ml]] 
[[dl]] 
[[rl]] 



_______
# PDL 2 - QUESTIONS

1. **Provide an example of where the bear classification model might work poorly in production, due to structural or style differences in the training data.**
Bear hidden in bushes
2. **Where do text models currently have a major deficiency?**
Can’t tell if they produce correct information
3. **What are possible negative societal implications of text generation models?**

4. **In situations where a model might make mistakes, and those mistakes could be harmful, what is a good alternative to automating a process?**
Be one cog/step in a multi step process involving manual checking
5. **What kind of tabular data is deep learning particularly good at?**
High cardinality categorical columns
6. **What's a key downside of directly using a deep learning model for recommendation systems?**
Doesnt’ recommend new things
7. **What are the steps of the Drivetrain Approach?**
What is the objective, what can you change to influence it, what data can you get, what model can you build
8. **How do the steps of the Drivetrain Approach map to a recommendation system?**

9. **Create an image recognition model using data you curate, and deploy it on the web.**
TO DO
10. **What is `DataLoaders`?**
Wrapper of dataloader → loads data to be used by model
11. **What four things do we need to tell fastai to create `DataLoaders`?**
What kind of data, how to get list of items, how to label, how to create validation set
12. **What does the `splitter` parameter to `DataBlock` do?**
Splitting validation/training
13. **How do we ensure a random split always gives the same validation set?**
Random seed
14. **What letters are often used to signify the independent and dependent variables?**
x, y
15. **What's the difference between the crop, pad, and squish resize approaches? When might you choose one over the others?**
Crop removes possibly vital information, pad makes it more inefficient, squish may alter image
16. **What is data augmentation? Why is it needed?**
Altering image without changing meaning → generalize
17. **What is the difference between `item_tfms` and `batch_tfms`?**
Applies to a single point of data vs batched data samples
18. **What is a confusion matrix?**
Tells you where it failed
19. **What does `export` save?**
Architecture + parameters + data loader definitions
20. **What is it called when we use a model for getting predictions, instead of training?**
Inference
21. **What are IPython widgets?**

22. **When might you want to use CPU for deployment? When might GPU be better?**

23. **What are the downsides of deploying your app to a server, instead of to a client (or edge) device such as a phone or PC?**

24. **What are three examples of problems that could occur when rolling out a bear warning system in practice?**

25. **What is "out-of-domain data"?**
Data not seen in testing data
26. **What is "domain shift"?**
Data becomes irrelevant
27. **What are the three steps in the deployment process?**




# References

