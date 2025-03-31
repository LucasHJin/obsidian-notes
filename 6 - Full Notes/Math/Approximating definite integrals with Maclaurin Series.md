2024-08-04 14:46

Status:


Tags:
[[math]]
[[school]]
[[calculus]]


___________________________________________________________________________
# Approximating definite integrals with Maclaurin Series

Can also be used to find approximations to definite integrals that otherwise would be difficult to evaluate
- You do this by just finding the expansion of the function, then integrate the first couple terms

**Example:** Use the first three terms of the Maclaurin expansion of $e^x$ to find an approximate value for $\int_0^1 {{e^{ - {x^2}}}} dx$.
- With substitution and [[Expansions of special functions|known expansions:]]
	- ${e^{ - {x^2}}} = 1 - {x^2} + \dfrac{{{x^4}}}{2} + {R_2}(- {x^2})$ 
- You can now take the definite integral of the series:
	- $\begin{align}\int_0^1 {{e^{ - {x^2}}}} dx &= \int_0^1 {\left({1 - {x^2} + \dfrac{{{x^4}}}{2} + \dots} \right)dx}  = \left[ {x - \dfrac{{{x^3}}}{3} + \dfrac{{{x^5}}}{{10}}} +\dots\right]_0^1 \\ &\approx1-\dfrac{1}{3}+\dfrac{1}{10}= \dfrac{{23}}{{30}} \end{align}$ 
- ![[Screenshot 2024-08-04 at 3.05.21 PM.png|300]] 
	- Approximations work locally


# References

