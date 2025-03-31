2024-08-13 10:27

Status:


Tags:
[[math]]
[[statistics]]
[[school]]


___________________________________________________________________________
# Standard normal distribution explained

Recap:
- [[Normal distribution explained]]
	- **Normal distribution:** A continuous distribution of data in which data points are clustered close to the mean, median and mode (which are approximately equal) and then decreases in frequency symmetrically on each side.
		- (Bell curve)
		- $X\sim{\rm{N}}\left({\mu,{\sigma ^2}} \right)$ 
	- Has limitations
		- I.e. trying to compare values from different normal distributions
	- Possible solutions:
		- Use **percentiles**: A value below which a given percentage of the data is included.
		- Use **==Standard Normal Distribution==**

**Standard Normal Distribution:** A normal distribution in which the mean $\mu = 0$ and the standard deviation $\sigma = 1$ 
- $Z\sim {\rm{N}}\left({0,1} \right)$ 
	- MEAN IS CENTERED AT $0$ 
- **Standard normal variable ($z$) ($z$-score):** $z = \dfrac{{x - \mu }}{\sigma }$ 
	- Transforms $X\sim{\rm{N}}\left({0,{\sigma ^2}} \right)$ into $Z\sim{\rm{N}}\left({0,1} \right)$ 
	- Equals the number of standard deviations away from the mean
	- Can use to switch between $X\sim{\rm{N}}\left({\mu,{\sigma ^2}} \right)$ and $Z\sim{\rm{N}}\left({0,1} \right)$ for a probability
		- $P(X<a)=P(Z<z)$ 
- **Finding probability with SND:**
	- Can do same as [[Normal distribution explained]]
		- I.e. using Normal CDF (just a special case)
	- Can represent rules as:
		- $\text{P}(- 1 < z < 1) \approx 0.68$ 
		- $\text{P}(- 2 < z < 2) \approx 0.95$ 
		- $\text{P}(- 3 < z < 3) \approx 0.997$ 
		- Because $\sigma$ is now $1$ 
			- Mean is at $0$ -> probability around that point
				- Symmetrical if $P(x>a)$ and $P(x<-a)$ 


**Example:** If $X\sim {\rm{N}}\left({3,0.4^2} \right)$ , find the 𝑧-scores for $x=3.5$.
- $z = \dfrac{{x - \mu }}{\sigma }=\dfrac{{3.5 - 3 }}{0.4 }=1.25$ 
	- Since $z$ is positive, this means that $x=3.5$ is $1.25$ standard deviations above the mean.

**Note:**
- You can find value of $z$ with $\text{P}(Z < z)$ because you always know the mean and standard deviation
	- Done with [[Normal distribution explained|inverse normal function]] 
	- Because $\mu=0, \sigma=1$ always
- Basically:
	- Given $P(X<a)=b$, you can plug in area=$b$ for $z=\frac{a-\mu}{\sigma}$ 
		- $\mu$ is the mean
	- If you are given 2 values -> convert both to $P(X<a)=b$:
		- Then, plug in and solve system of equations for $\mu, \sigma$ 



# References

