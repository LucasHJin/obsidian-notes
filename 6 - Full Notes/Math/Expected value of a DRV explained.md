2024-08-12 12:26

Status:


Tags:
[[math]]
[[statistics]]
[[school]]
[[game theory]]


___________________________________________________________________________
# Expected value of a DRV explained

**Expected value ($E(X)$):** The value you would expect to obtain on average if you performed an experiment many times.
- For a random variable $X$ with [[Probability distributions and DRV explained|probability distribution]] $P(X=x)$:
	- $\begin{align} \rm{E}(X)&=\mu = \sum_{i=1}^{N} x_i \rm{P}(X=x_i)\\ &=x_1 \rm{P}(X=x_1)+ x_2 \rm{P}(X=x_2)+ x_3 \rm{P}(X=x_3)+\textrm{...}+ x_N \rm{P}(X=x_N) \end{align}$ 
		- Similar to [[Cumulative frequency curves explained|mean of frequency distribution]] 
	- Just probability of each one times the value of each one added up

*In discrete distributions it is common for the expected value **not** to be one of the actual outcomes of the experiment* 

**Fair game:** An experiment involving two parties, also known as a game, in which the expected value $E(X)=0$.
- Basically where the expected payout for either side is $0$ -> so that its fair for both sides

**Example:** A game for two players uses a 20-sided dice. If Player A rolls a prime number, they win 5 points. Otherwise, Player B wins $k$ points. If the random variable $X$ represents how many points Player A is winning by, find the value of $k$ that makes this a fair game.
- Just make $E(X)=0$
- Number of primes $=8$ 
- $E(X)=A\text{ wins}+B\text{ wins}$ 
- $E(X)=\frac{8}{20}\cdot 5+\frac{12}{20}\cdot (-k)=0$
- $\therefore k=\frac{10}{3}$ 






# References

