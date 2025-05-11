2024-08-12 14:00

Status:


Tags:
[[math]]
[[statistics]]
[[hs]]
[[probability]]


___________________________________________________________________________
# Probability in binomial distribution explained

Can use a tree diagram
- ![[Screenshot 2024-08-12 at 2.15.00 PM.png|400]] 
$\begin{align}\text{P}(D\geqslant 2)&=\text{P}(D=2)+\text{P}(D=3)+\text{P}(D=4)\\   & =6(0.7\times 0.7\times 0.3\times 0.3)+4(0.7\times 0.3\times 0.3\times 0.3)+(0.3\times 0.3\times 0.3\times 0.3) \\  & =0.2646+0.0756+0.0081 \\  & =0.3483\approx 0.348  \end{align}$
- [[Modelling related events - Probability]] 
- Is tedious for larger values of $n$ 

==**Formula:**==
- $X\sim B(n,p)\Rightarrow \rm{P}(X=x)= \begin{pmatrix}n\\x\end{pmatrix} p^x(1-p)^{n-x}$ 
	- $\begin{pmatrix}n\\x\end{pmatrix}={^n C_x}=\dfrac{n!}{x! (n-x)!}$ 
	- Basically just number of possible ways to order $\cdot$ number of success vs fail
- 

**CAN ALSO USE A CALCULATOR TO CALCULATE PROBABILITY DISTRIBUTION FUNCTION (PDF)** 
- Requires: $n$, $p$, $x$ (for $P(X=x)$)
- Can also use **GDC binomial cumulative distribution function**:
	- To return probability of a range of values
- **NOTE**:
	- The TI-84 requires you to enter 𝑛, 𝑝 and an upper bound and returns $\rm{P}(0\leqslant X\leqslant \textrm{upper bound})$ .
- binompdf or binomcdf
- Remember: $\rm{P}(a\leqslant X\leqslant b)= \rm{P}(0\leqslant X\leqslant b)- \rm{P}(0\leqslant X\leqslant a-1)$ 
	- Needs to be one value lower
- Or binomial PDF with summation function




# References
https://app.kognity.com/study/app/hl1/sid-134-cid-253042/book/calculating-bionomial-probabilities-id-25663/ 
