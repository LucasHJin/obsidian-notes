2024-08-14 11:51

Status:


Tags:
[[math]]
[[statistics]]
[[hs]]
[[probability]]



___________________________________________________________________________
# Mean and variance of a CRV explained

Review:
- [[Measures of CT and D explained]] 
	- Mean -> avg
	- Variance -> for examining spread


___ 
**Mean of a CRV:** Equal to the expectation (Just like for [[Discrete random variables and measures of dispersion explained|DRVs]])
- $\mu={\rm{E}}\left(X \right) = \int_a^b {x\;f\left(x \right)\,{\rm{d}}x}$ 
	- Area under the curve $\cdot$ the amount of density at that area


**Variance of a CRV:** Similar to DRV in that it is the summation (just infinite)
- ${\rm{Var}}\left(X \right) = \int_{ - \;\infty }^\infty  {{{\left({x - \mu } \right)}^2}} f\left(x \right){\rm{d}}x=\int_{a}^{b}{{{x}^{2}}}f(x)\,\text{d}x-{{\mu }^{2}}$  
	- Remember $\mu=E(X)$ 
	- Not necessarily $-\infty, \infty$ -> can just be domain


___
**Example:** 
- $\begin{align} {\rm{E}}\left(X \right) &= \int_0^4 {x\;f\left(x \right)\;{\rm{d}}x} \\ & = \int_0^2 {x\left({\dfrac{1}{4}x} \right){\rm{d}}x + \int_2^4 {x\left({ - \dfrac{1}{4}x + 1} \right){\rm{d}}x} } \\  &= \int_0^2 {\dfrac{1}{4}{x^2}{\rm{d}}x}  + \int_2^4 { - \dfrac{1}{4}{x^2} + x{\rm{d}}x} \\  &= \left[ {\dfrac{1}{{12}}{x^3}} \right]_{0}^{2} + \left[ { - \dfrac{1}{{12}}{x^3} + \dfrac{1}{2}{x^2}} \right]_{2}^{4}\\  &= \left({\dfrac{1}{{12}}\left(8 \right) - \dfrac{1}{{12}}\left(0 \right)} \right) + \left({ - \dfrac{1}{{12}}\left({{4^3}} \right) + \dfrac{1}{2}\left({{4^2}} \right) - \left({ - \dfrac{1}{{12}}\left({{2^3}} \right) + \dfrac{1}{2}\left({{2^2}} \right)} \right)} \right)\\  &= \dfrac{8}{{12}} - \dfrac{{64}}{{12}} + 8 + \dfrac{8}{{12}} - 2\\  &= 2 \end{align}$ 
- $\begin{align} {\rm{Var}}\left(X \right) &= \int_0^2 {{{\left({x - 2} \right)}^2}} \left({\dfrac{1}{4}x} \right){\rm{d}}x + \int_2^4 {{{\left({x - 2} \right)}^2}\left({ - \dfrac{1}{4}x + 1} \right){\rm{d}}x} \\  &= \int_0^2 {\left({\dfrac{1}{4}{x^3} - {x^2} + x} \right){\rm{d}}x}  + \int_2^4 {\left({ - \dfrac{1}{4}{x^3} + 2{x^2} - 5x + 4} \right){\rm{d}}x} \\  &= \left[ {\dfrac{1}{{16}}{x^4} - \dfrac{1}{3}{x^3} + \dfrac{1}{2}{x^2}} \right]_{0}^{2} + \left[ { - \dfrac{1}{{16}}{x^4} + \dfrac{2}{3}{x^3} - \dfrac{5}{2}{x^2} + 4x} \right]_{2}^{4}\\  &= \left({1 - \dfrac{8}{3} + 2} \right) + \left({ - 16 + \dfrac{{128}}{3} - 40 + 16 - \left({ - 1 + \dfrac{{16}}{3} - 10 + 8} \right)} \right)\\  &= \dfrac{2}{3} \end{align}$ 



# References

