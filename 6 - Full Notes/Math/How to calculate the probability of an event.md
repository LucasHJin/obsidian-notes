2024-08-10 22:21

Status:


Tags:
[[math]]
[[statistics]]
[[school]]
[[probability]]


___________________________________________________________________________
# How to calculate the probability of an event

This is assuming ==**random experiment==:** An experiment where all possible results are known and occur with consistent probabilities
- **Sample space** ($U$): Set of all possible outcomes of a random experiment
	- I.e. for a dice -> $U= \left \{ 1,2,3,4,5,6 \right \}$ 
	- **Event**: Any subset of $U$ with $1+$ outcomes
- **Number of possible outcomes** = $n(U)$ 
	- I.e. for a dice -> $n(U)=6$ 
- **Trial:** 1 occurrence of an experiment
	- Will have one outcome from the sample space

2 types of probability:
- **Experimental probability** (relative frequency): found inductively by repeating an experiment a number of times and counting the number of times that particular outcome occurs
	- For a ==random experiment== -> will have long term regularity/pattern
		- I.e. rolling a dice 6000 times will have ~1000 rolls of 1
		- Will approach ==theoretical probability== for large number of trials
	- **Consider mutual exclusivity:** Outcomes are not shared
		- I.e. can't have 1 and 2 at the same time
	- $\rm{P}(A)=\lim_{N\rightarrow \infty}\dfrac{n(A)}{N}$ 
- **Theoretical probability:** calculated from general formula and guaranteed knowledge
	- $P(A)=\dfrac{n(A)}{n(U)}=\dfrac{\text{Number of outcomes in which A occurs}}{\text{Total number of outcomes in the sample space}}$ 

**Axioms of probability:**
- For any event $A, 0\leqslant \rm{P}(A) \leqslant 1$ 
- Probability of nothing ($\text{o}$) $=P(\text{o})=0$ 
	- Probability of an outcome occurring $=P(U)=1$ 
- If $A,B\in U$ and $A,B$ are mutually exclusive:
	- Probability of $A$ or $B$ $=\rm{P}(A\cup B)=\rm{P}(A)+\rm{P}(B)$ 
		- $\cup$ is union -> either one happens

**Complement to an event:** All of the other events in the sample space
- i.e. $A$ and $A'$ -> $P(A)+ P({A}')=1$ 
	- Can use **complementary counting** 
		- Subtract what you don't want to get what you do
		- $1-P(A')$ 

[[Combinations vs Permutations]]




# References

