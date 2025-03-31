2024-08-12 12:41

Status:


Tags:
[[math]]
[[statistics]]
[[school]]


___________________________________________________________________________
# Binomial distribution explained

**Binary event:** An event that has only two possible outcomes
- Don't necessarily need to be weighted the same
	- I.e. chances of rolling a 5 vs not rolling a 5 on a dice
- The outcomes are complementary events -> add up to $1$ 

**Binomial experiments:** An experiment consisting of a finite number of repeated trials that are identical, independent, binary events.
- Basically just multiple binary events
	- I.e. See if you roll a $5$ or not $50$ times 
- **==Discrete binomial distribution==**: A probability distribution $X\sim B(n,p)$ consisting of $n$ repeated, independent trials whose probability of success each trial is $p$.

**Binomial distribution:** $X\sim B(n,p)$
- **Notation and parameters:**
	- $p:$ probability of success (event occurring)
		- probability of an event occurring a certain number of times
	- $q:$ probability of failure
		- $q=1-p$ 
	- $X\sim:$ denotes that a random variable $X$ is distributed a certain way
	- $n:$ number of trials in the binomial experiment
	- $B:$ name of the distribution
- **Example:** find  the probability of a certain number of rainy days in June, given a $0.3$ experimental probability that it rains on any given day
	- $X\sim B(30, 0.3)$ 
		- $\operatorname{E}(X)=30*0.3=10$ 
		- $\operatorname{Var}(X)=30*0.3(1-0.3)=6.3$ 
- *Each binomial distribution has an expected value*
	- Probability of success is equal for each event
	- $\operatorname{E}(X)=np$ 
		- [[Expected value of a DRV explained]]
	- $\operatorname{Var}(X)=np(1-p)$ 
		- [[Measures of dispersion explained]] 


**[[Probability in binomial distribution explained]]**




# References

