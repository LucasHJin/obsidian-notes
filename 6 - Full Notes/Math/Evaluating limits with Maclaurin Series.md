2024-08-04 14:46

Status:


Tags:
[[math]]
[[school]]
[[calculus]]


___________________________________________________________________________
# Evaluating limits with Maclaurin Series

- You can evaluate with limits with MS
	- (including indeterminate forms - instead of L'Hopital's rule)
- Generally, you want something of the form of $\frac{f(x)-x}{x}$ 
	- Then, you can cancel some terms, divide the rest by denominator -> all will be removed by limit except 1
- ==Trick:==
	- Can normally sub $n=\frac{1}{x}$ if you see $\sqrt{n^2-1}$ or $\sqrt{n^2+1}$ 
		- Because $\sqrt{n^2-1}$ doesn't work, only $\sqrt{1-n^2}$ 

**Example:** $\mathop {\lim }\limits_{x \to 0} \dfrac{{{e^x} - 1 - x}}{{{x^2}}}$ 
- **Option 1:** take L'Hopital's rule twice
	- ($\mathop {\lim }\limits_{x \to 0} \dfrac{{f(x)}}{{g(x)}} = \mathop {\lim }\limits_{x \to 0} \dfrac{{f'(x)}}{{g'(x)}}$)
	- $\mathop {\lim }\limits_{x \to 0} \dfrac{{{e^x} - 1 - x}}{{{x^2}}} =\mathop {\lim }\limits_{x \to 0} \dfrac{{{e^x} - 1}}{{2x}} = \mathop {\lim }\limits_{x \to 0} \dfrac{{{e^x}}}{2} = \dfrac{{{e^0}}}{2} = \dfrac{1}{2}$ 
- **Option 2:** Notice that there is $e^x$ so use the MS of $e^x$ 
	- ${e^x} = 1 + x + \dfrac{1}{{2!}}{x^2} + \dfrac{1}{{3!}}{x^3} + ...$ 
	- Now substitute:
	- $\qquad\begin{array}{l} \mathop {\lim }\limits_{x \to 0} \dfrac{{{e^x} - 1 - x}}{{{x^2}}} &= \mathop {\lim }\limits_{x \to 0} \dfrac{{\left({1 + x + \dfrac{1}{{2!}}{x^2} + \dfrac{1}{{3!}}{x^3} + ...} \right) - 1 - x}}{{{x^2}}}\\  &= \mathop {\lim }\limits_{x \to 0} \dfrac{{\dfrac{1}{{2!}}{x^2} + \dfrac{1}{{3!}}{x^3} + ...}}{{{x^2}}}\\& = \mathop {\lim }\limits_{x \to 0} \left({\dfrac{1}{{2!}} + \dfrac{x}{{3!}} + \dfrac{{{x^2}}}{{4!}} + \dfrac{{{x^3}}}{{5!}} + ...} \right) = \dfrac{1}{2} \end{array}$
		- Because only the constant stays the same -> all other values approach $0$ 




# References

