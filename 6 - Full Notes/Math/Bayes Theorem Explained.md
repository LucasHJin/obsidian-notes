2024-08-13 15:08

Status:


Tags:
[[math]]
[[statistics]]
[[school]]
[[probability]]



___________________________________________________________________________
# Bayes Theorem Explained

**False positive:** A statistical test result that incorrectly states an event occurred.
- It says true but is actually false

**[[Conditional probability and independence explained|Conditional probability]]:** The probability of an event given that another event has occurred.
- ${\rm{P}}\left({\left. {A\;} \right|B} \right)$ - the probability of A given B
	- What is the probability that the event falls in the red circle given that it is in the blue circle
	- ![[Screenshot 2024-08-13 at 7.37.44 PM.png|300]] 
- $\begin{align} {\rm{P}}\left({\left. {A\;} \right|B} \right) &= \frac{{{\rm{P}}\left({A \cap B} \right)}}{{{\rm{P}}\left(B \right)}}\;\;\; \to \;\;\;{\rm{P}}\left({A \cap B} \right) = {\rm{P}}\left(B \right)\,{\rm{P}}\left({\left. {A\;} \right|B} \right)\\ {\rm{P}}\left({\left. {B\;} \right|A} \right) &= \frac{{{\rm{P}}\left({B \cap A} \right)}}{{{\rm{P}}\left(A \right)}}\;\;\; \to \;\;\;{\rm{P}}\left({B \cap A} \right) = {\rm{P}}\left(A \right)\,{\rm{P}}\left({\left. {B\;} \right|A} \right) \end{align}$ 
	- Rearranged to the intersection of $A$ and $B$
	- **Commutative property for intersection:** ${\rm{P}}\left({A \cap B} \right) = {\rm{P}}\left({B \cap A} \right)$ 
- $\therefore \rm{P}\left({\left. {A\;} \right|B} \right) = \dfrac{{\rm{P}\left(A \right)\,\rm{P}\left({\left. {B\;} \right|A} \right)}}{{\rm{P}\left(B \right)}}$ 
	- ==One version of Bayes' theorem== 


____

**Bayes Theorem:** An extension of conditional probability used to calculate the probability of a prior event based on the known probability of a current event.

**2 Events:** 
- ${\rm{P}}\left({\left. {A\;} \right|B} \right) = \dfrac{{{\rm{P}}\left({A \cap B} \right)}}{{{\rm{P}}\left(B \right)}} = \dfrac{{{\rm{P}}\left(A \right)\,{\rm{P}}\left({\left. {B\;} \right|A} \right)}}{{{\rm{P}}\left(A \right)\,{\rm{P}}\left({\left. {B\;} \right|A} \right) + {\rm{P}}\left({A'} \right)\,{\rm{P}}\left({\left. {B\;} \right|A'} \right)}}$ 
- Can use [[Modelling related events - Probability|tree diagrams]] to visualize
	- ![[Screenshot 2024-08-13 at 8.48.42 PM.png|400]] 
		- Same as arrow notation ($A|B\rightarrow A\cap B$)
- Can think of it just as:
	- chance of winning A and B / all possibilities where you win B

**3 Events:** 
- ${\rm{P}}\left({\left. {{A_{\;i}}\;} \right|B} \right) = \dfrac{{{\rm{P}}\left({{A_{\;i}}} \right){\rm{P}}\left({\left. {B\;} \right|{A_{\;i}}} \right)}}{{{\rm{P}}\left({{A_{\;1}}} \right){\rm{P}}\left({\left. {B\;} \right|{A_{\;1}}} \right) + {\rm{P}}\left({{A_{\;2}}} \right){\rm{P}}\left({\left. {B\;} \right|{A_{\;2}}} \right) + {\rm{P}}\left({{A_{\;3}}} \right){\rm{P}}\left({\left. {B\;} \right|{A_{\;3}}} \right)}}$ 
- ![[Screenshot 2024-08-13 at 9.19.45 PM.png|400]] 
	- Since you can add up the $B$ paths to get $P(B)$:
		- $\begin{align} {\rm{P}}\left(B \right) &= {\rm{P}}\left({{A_{\;1}} \cap B} \right) + {\rm{P}}\left({{A_{\;2}} \cap B} \right) + {\rm{P}}\left({{A_{\;3}} \cap B} \right)\\  &= {\rm{P}}\left({{A_{\;1}}} \right){\rm{P}}\left({\left. {B\;} \right|{A_{\;1}}} \right) + {\rm{P}}\left({{A_{\;2}}} \right){\rm{P}}\left({\left. {B\;} \right|{A_{\;2}}} \right) + {\rm{P}}\left({{A_{\;3}}} \right){\rm{P}}\left({\left. {B\;} \right|{A_{\;3}}} \right) \end{align}$ 




# References

