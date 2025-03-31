2024-08-03 22:25

Status:


Tags:
[[math]]
[[school]]
[[calculus]]


___________________________________________________________________________
# Expansions of special functions

*These are important Maclaurin series expansions that can be manipulated to find the expansions of more complicated functions*

**Exponential function:** 
${{\rm{e}}^x} = 1 + x + \dfrac{{{x^2}}}{{2!}} + \dfrac{{{x^3}}}{{3!}} +  \cdots  = \sum\limits_{n = 0}^\infty  {\dfrac{{{x^n}}}{{n!}}}$ 
- ==Can be used for approximation for all real numbers $x$ ==

**Natural logarithm:** 
$\ln (1 + x) = x - \dfrac{{{x^2}}}{2} + \dfrac{{{x^3}}}{3} -  \cdots  = \sum\limits_{n = 1}^\infty  {{{(- 1)}^{n + 1}}\dfrac{{{x^n}}}{n}}$ 
- ==Can be used for approximation for $|x|<1$ and $x=1$ ==

**Sine function:** 
$\sin x = x - \dfrac{{{x^3}}}{{3!}} + \dfrac{{{x^5}}}{{5!}} -  \cdots  = \sum\limits_{n = 0}^\infty  {\dfrac{{{{(- 1)}^n}}}{{(2n + 1)!}}{x^{2n + 1}}}$ 
- ==Can be used for approximation for all $x$ ==

**Cosine function:** 
$\cos x = 1 - \dfrac{{{x^2}}}{{2!}} + \dfrac{{{x^4}}}{{4!}} -  \cdots  = \sum\limits_{n = 0}^\infty  {\dfrac{{{{(- 1)}^n}}}{{(2n)!}}{x^{2n}}}$ 
- ==Can be used for approximation for all $x$ ==

**Inverse tangent function:** 
$\arctan x = x - \dfrac{{{x^3}}}{3} + \dfrac{{{x^5}}}{5} -  \cdots  = \sum\limits_{n = 0}^\infty  {\dfrac{{{{(- 1)}^n}}}{{2n + 1}}{x^{2n + 1}}}$ 
- ==Can be used for approximation for $|x|\leq 1$ ==

**[[Binomial series explained|Binomial series:]]**
${(1 + x)^p} = 1 + px + \dfrac{{p(p - 1)}}{{2!}}{x^2} + \dfrac{{p(p - 1)(p - 2)}}{{3!}}{x^3} + \cdots= \sum\limits_{n = 0}^\infty  {\left({\begin{array}{*{20}{c}} p\\ n \end{array}} \right){x^n}}$ 
- ==Can be used for approximation for $-1<x\leq 1$ ==

___
**Manipulation example:**
- If you know the Maclaurin series expansion for $\sin x$, then you can take derivative (manipulate it) to get the Maclaurin series expansion of $\cos x$ 
$\qquad\qquad\begin{align} \dfrac{{\rm{d}}}{{{\mathop{\rm d}\nolimits} x}}\left({\sin x} \right) &= \dfrac{{\rm{d}}}{{{\rm{d}}x}}\left({x - \dfrac{{{x^3}}}{{3!}} + \dfrac{{{x^5}}}{{5!}} -  \cdots } \right)\\ \cos x &= 1 - 3\dfrac{{{x^2}}}{{3!}} + 5\dfrac{{{x^4}}}{{5!}} -  \cdots  = 1 - \dfrac{{{x^2}}}{{2!}} + \dfrac{{{x^4}}}{{4!}} -  \cdots  = \sum\limits_{n = 0}^\infty  {\dfrac{{{{(- 1)}^n}}}{{(2n)!}}{x^{2n}}} \end{align}$ 

**Manipulation:**
- Using substitution, multiplication, addition, subtraction, division, composition, differentiation and integration
	- I.e. can first take derivative of $ln(cos(x))$ to get $\tan x$ which equals $\frac{\sin x}{\cos x}$ 
		- You can divide the known expansions with long division
		- And reverse finally with integratino

==**VERY IMPORTANT:**==
- Can sub in entire polynomials for $x$
	- I.e. sub in $x^2+x$ for x
		- Then calculate for a coefficient with binomial expansions

# References
https://app.kognity.com/study/app/hl1/sid-134-cid-253042/book/expansion-of-special-functions-id-27286/


___
==TO NOTE==
- When manipulating, you can just multiply the two together if you just want the first couple terms (expansion multiplication)
- For trig:
	- You can use trig formulas (i.e. double angle)
- Can perform normal operations on the expansions
	- I.e. integrating and expansion