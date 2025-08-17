2025-08-09 14:50

Status:


Tags:
[[uni]] 
[[m135]] 


_______
# m135 - Proof by Contrapositive

**Proof by contrapositive:** proving a statement that is logically equivalent to the given implication
- I.e. to prove “$A\implies B$” → prove the contrapositive “$\neg B\implies \neg A$” using a [[m135 - Proving Implications|direct proof]] 
	- Assume $\neg B$ is true and prove $\neg A$ 
- To prove the UQI “$\forall x\in S, P(x)\implies Q(x)$“ → prove the contrapositive 
	- “$\forall x\in S, (\neg Q(x))\implies (\neg P(x)))$” 
- **Method of elimination:** $A\implies B\vee C\equiv A\land \neg B\implies C$ 
	- Eliminates the possibility of component $B$ in original implication’s conclusion → prove that component $C$ is true

**Example:** 
- ![[Screenshot 2025-08-09 at 5.51.49 PM.png]] 
**Use cases:** 
- When the hypothesis seems more complicated than the conclusion
- When the conclusion is a disjunction ($A\implies B\vee C$) 
	- Contrapositive becomes $\neg B\land \neg C\implies \neg A$ 
		- After applying De Morgan’s Law ^




# References

