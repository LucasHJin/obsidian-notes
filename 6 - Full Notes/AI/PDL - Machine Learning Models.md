2025-08-29 16:54

Status:


Tags:



_______
# PDL - Machine Learning Models

*At a high level:* 
- **Normal computer program:** inputs → program → output 
- **Machine learning model:** ![[Screenshot 2025-08-29 at 4.57.16 PM.png]]
	- **Model** → mathematical function that takes inputs and multiplies by one set of weights and adds them up
		- Repeats for all sets of weights
		- Takes all negative numbers and replaces with 0s
		- Takes that as inputs and repeats for a certain number of layers
		- Special type of program that can be changed based on weights
	- **Weights** → initially random (not useful)
		- ![[Screenshot 2025-08-29 at 4.59.46 PM.png]] 
		- Calculates loss from results (i.e. how accurate they were) and then uses it to update/fine tune the weights 
		- *Note* → generally called **parameters** 
	- **Computable function:** any task that takes an input and gives an output (i.e. translate)
		- Eventually becomes like normal computer program that can be called

**Parallel Distributed Processing (PDP):** style of computing/processing that allows computers to mimic the processing method of the brain
- Requires:
	- A set of *processing units*
	- A state of *activation*
	- An *output function* for each unit
	- A *pattern of connectivity* among units
	- A *propagation rule* for propagating patterns of activities through the network of connectivities
	- An *activation rule* for combining the inputs impinging on a unit with the current state of that unit to produce an output for the unit
	- A *learning rule* whereby patterns of connectivity are modified by experience
	- An *environment* within which the system must operate

**General idea:** 
> Suppose we arrange for some automatic means of testing the effectiveness of any current weight assignment in terms of actual performance and provide a mechanism for altering the weight assignment so as to maximize the performance. We need not go into the details of such a procedure to see that it could be made entirely automatic and to see that a machine so programmed would "learn" from its experience.
> *- Arthur Samuel* 

# References

