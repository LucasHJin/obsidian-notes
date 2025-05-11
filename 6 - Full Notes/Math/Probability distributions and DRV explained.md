2024-08-12 12:10

Status:


Tags:
[[math]]
[[statistics]]
[[hs]]
[[probability]]



___________________________________________________________________________
# Probability distributions and DRV explained

*Random variables are capitalized, values they take are lower case:*
- $X$ vs $x$ 
- If a random variable $X$ can take exactly $N$ values -> is a **[[Discrete random variables explained|discrete random variable]]** 

**Example:** Tossing a coin 3 times. Let the number of heads be the random variable.
- **Sample space:** $\left \{ HHH,HHT,HTH,THH,HTT,THT,TTH,TTT\right \}$ 
- $X=x, x\in \left\{ 0,1,2,3 \right\}$ 
- Probability that $X$ takes on these values = $P(X=x)$ 
	- I.e. $\rm{P}(X=2)=\rm{P}(HHT)+P(HTH)+\rm{P}(THH)=\dfrac{1}{8}+\dfrac{1}{8}+\dfrac{1}{8}=\dfrac{3}{8}$ 
	- $P(X\geq x_i)$ means probability of all from value of $x_i$ and up
- **For probability distribution:** a combination of the sample space of a random experiment with the probabilities of each of the events in the sample space
	- Calculate for every $P(X=x)$ the probability:
	- ![[Screenshot 2024-08-12 at 12.16.28 PM.png]] 

**==Properties of probability distribution: (WELL DEFINED)==**
- For each value $x_i$ of the random variable $X$:
	- $0\leqslant \rm{P}(X=x_i)\leq 1$ 
	- Probability of any 1 case between $0$ and $1$ 
- $\displaystyle{\sum_{i=1}^{N}\rm{P}(X=x_i)=\rm{P}(X=x_1)+\rm{P}(X=x_2)+...+\rm{P}(X=x_N)=1}$ 
	- The sum of all the probabilities must be 1

**Infinite discrete random variables can show up**
- Just use infinite summations to calculate desired values (arithmetic/geometric sequences)



# References

