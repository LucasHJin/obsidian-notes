2025-08-09 21:22

Status:


Tags:
[[uni]] 
[[m145]] 

_______
# m135 - Induction

*Notes:* 
- Useful → [[m135 - Summation, Product, Recurrence Notation]]
- **Axiom:** a mathematical system is a statement that is assumed to be true (no proof needed)
	- From axioms we derive [[m135 - Proofs|propositions and theorems]] 
- More:
	- [[m135 - Binomial Theorem]]

**Principle of Mathematical Induction (POMI):** 
- **Axiom:**
	- Let $P(n)$ be an open sentence that depends on $n\in N$ 
		- If these two statements are true:
			- $P(1)$ 
			- For all $k\in N$, if $P(k)$ then $P(k+1)$ 
		- Then it can be proven that for all $n\in N$, $P(n)$ is true
- *Is an axiom that defines the properties of a mathematical system*
- **Proof method:** 
	- Show that $P(1)$ (or any other base case) holds and then prove that for all $k\in N$, if $P(k)$ then $P(k+1)$ 
	- **Base case** → part 1 of the proof statement
	- **Inductive step** → part 2 of the proof statement (the implication $P(k)\implies P(k+1)$) 
		- **Inductive hypothesis** → hypothesis of implication
		- **Inductive conclusion** → conclusion of implication
	- *General format:* to prove that for all $n\in N$, $P(n)$ 
		- State that the proof is by induction on $n$ and identify the open sentence $P(n)$ 
		- Prove/verify $P(1)$ 
		- Assume $P(k)$ → write out the open sentence
		- Prove $P(k+1)$ → also write out open sentence before giving the proof (i.e. “wi wish to prove”)
		- End the proof stating that it works for $n=k+1$ so it holds by the POMI
	- **IF:** it is $n\geq b$, prove $P(n)$ (called induction with starting point $b$)
		- Then prove $P(b)$ for base case
		- And assume that $k$ is an arbitrary integer with $k\geq b$ and continue from there

**Principle of Strong Induction (POSI):** For when POMI can’t prove because you need to assume more than just one specific value of an open statement 
- I.e. assume $P(k), P(k-1), P(k-2), ...$ 
- **Axiom:** 
	- Let $P(n)$ be an open sentence that depends on $n\in N$ 
		- If these two statements are true:
			- $P(1)$ 
			- For all $k\in N$, if $P(1)\land P(2)\land \ldots \land P(k)$ then $P(k+1)$ 
		- Then it can be proven that for all $n\in N$, $P(n)$ is true
- **Proof method:** To prove “For all integers $n\geq b, P(n)$”
	- Prove the base case “$P(b)\land P(b+1)\land\ldots\land P(B)$ for some integer $B\geq b$”
	- Prove the UQI “For some integer $k\geq B$, if $P(b)\land P(b+1)\land\ldots\land P(k)$, then $P(k+1)$” 
		- Assume $P(i)$ for $i=b...k$ and prove for $k+1$ 

**Example:** 
- [[MATH 135 Course Notes.pdf]] 
	- Page 68
	- Page 78




# References

