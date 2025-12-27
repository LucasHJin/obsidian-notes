2025-12-26 16:07

Status:


Tags:
[[cs]] 
[[ai]] 
[[rl]] 
[[ml]] 


_______
# RL - Bias vs Variance Tradeoff

*Note* → different from the [[PDL 4 - Overfitting|ML supervised learning BV tradeoff]] (overfitting)
- Bias → how far average learned model is from true function
	- I.e. higher bias = worse prediction
- Variance → how much the learned model changes when data changes
	- I.e. higher variance = overfitting 
- Tradeoff → if a model is bigger it is better able to model but may overfit
- *Regularization* → intentionally adding bias to reduce variance (because for big data sets, variance generally is worse)
	- L2 / weight decay → shrink all weights
	- L1 → push small weights close to 0
	- Dropout → train a new network each time by deleting random neurons
	- Data augmentation → add more distinct data
	- Early stopping → stop early once validation loss stops improving
^ RL deals with BOTH this and a separate BV tradeoff

**RL Bias Variance Tradeoff:** how well the reinforcement signal (actual numeric reward) reflects the true reward structure of the environment (real objective → no reward hacking)
- *Credit assignment* → giving credit to the series of actions that lead to a reward
	- AKA a [[RL - Value Based Methods|value estimate]] 
- Variance → noisy but accurate value estimate
- Bias → stable (doesn’t change much) but inaccurate value estimate
- *Solutions:* 
	- Advantage learning → use a baseline to subtract from reward signal for more stable “Advantage” $A(s,a)$ 
		- I.e. subtract using a more stable learned value function



# References

