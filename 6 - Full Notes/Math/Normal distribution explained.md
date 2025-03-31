2024-08-12 15:05

Status:


Tags:
[[math]]
[[statistics]]
[[school]]
[[probability]]


___________________________________________________________________________
# Normal distribution explained

**Normal distribution:** A ==continuous== distribution of data in which data points are clustered close to the mean, median and mode (which are approximately equal) and then decreases in frequency symmetrically on each side.
- Most widely known probability distribution function
	- (also called bell curve)
- Deals with **continuous random variables** (not discrete):
	- Any real number within the range of realistic possible values, measured

**Graphical representation:** Normal (bell) curve
- A clustering around the centre with its tails falling off on each side
	- (largest point in middle, decreases quickly on each side)
	- Is symmetric
- Highest point always in the center (**mean - $\mu$, median and mode**)
- Horizontal axis = intervals of **standard deviation** ($\sigma$)
- Probability of a random variable falling in a specific range = [[Derivative and Integration CheatSheet|area under the curve]] 
- ![[Screenshot 2024-08-12 at 7.02.24 PM.png|300]]
	- I.e. $\mu=167$, $\sigma=3$, $\rm{P}(164\leqslant X \leqslant 170)$ is shaded
- **TO NOTE:**
	- Manipulating $\mu$ = horizontal translation
	- Manipulating $\sigma$ = horizontal and vertical stretches/compressions
		- I.e. bigger $\sigma$ = wider range, bigger stretch
			- Bigger -> shorter and wider
			- Smaller -> taller and thinner

**Algebraic representation:** $X \sim N(\mu ,\sigma ^2)$ 
- $X \sim:$ denotes that a random variable $X$ **is distributed** a certain way
- $\mu:$ the mean of the normal curve
- $\sigma^2:$ the variance of the normal curve
	- Written with the $^2$, I.e. $X \sim N(10 ,3 ^2)$ 
- Can also use **normal probability density function**:
	- Depends once again on $\mu$ and $\sigma$ (2 parameters)
	- $f(x)=\dfrac{1}{\sigma \sqrt{2\pi}}e^{\dfrac{-1}{2}\left (\dfrac{x-\mu }{\sigma }\right )^2},x\in(-\infty, \infty)$ 
		- *Theoretically, for a sample space, normal distribution is set of real numbers* 
- Since the sum of all probabilites must equal $1$ in total:
	- $\displaystyle{\int_{-\infty}^{\infty}\dfrac{1}{\sigma \sqrt{2\pi}}e^{\dfrac{-1}{2}\left (\dfrac{x-\mu }{\sigma }\right )^2}dx=1}$ 
- Basically just represents that data is distributed normally (not probability itself)

**Probabilities in normal distribution:**
- Probability of an event = integral of the PDF (area under curve)
1. The probability that $X$ has a value within an interval $a\leq x\leq b$ 
	1. ![[Screenshot 2024-08-12 at 8.23.09 PM.png|350]] 
		1. Can also use complement for this if equal distance from mean
		2. $1-(P(X<a)+P(X>b))$ 
2. The probability that $X$ has a value greater than (or less than) a certain measure 
	1. ![[Screenshot 2024-08-12 at 8.23.28 PM.png|350]] 
		1. Can also complementary counting
3. The probability that $X$ has a value beyond a certain distance from the mean
	1. ![[Screenshot 2024-08-12 at 8.23.40 PM.png|350]] 
- **Example:** Probability that a normally distributed variable lies within a given range of $X\sim N(2,1.5^2)$ 
$\operatorname{P}(1.2 < X < 3.5)\\ =\dfrac{1}{1.5\sqrt{2\pi}}\int_{1.2}^{3.5} \operatorname{e}^{-\frac{1}{2}\left(\frac{x-2}{1.5} \right)^2}\mathrm{d}x\\ \approx 0.544$ 
$\operatorname{P}(X < 1.2)\\ =\dfrac{1}{1.5\sqrt{2\pi}}\int_{-\infty}^{1.2} \operatorname{e}^{-\frac{1}{2}\left(\frac{x-2}{1.5} \right)^2}\mathrm{d}x\\ \approx 0.297$ 
$\operatorname{P}(X < 2-1.5=0.5)\\ =\dfrac{1}{1.5\sqrt{2\pi}}\int_{-\infty}^{0.5} \operatorname{e}^{-\frac{1}{2}\left(\frac{x-2}{1.5} \right)^2}\mathrm{d}x\\ \approx 0.159=\operatorname{P}(X > 2+1.5=3.5)$ 
- The percentile equals the calculated probability
	- I.e. percentile of $1.2$ is ~$30$% 
- REMEMBER:
	- $\operatorname{P}(X < b)=\operatorname{P}(X < a)+\operatorname{P}(a < X < b)$ 


==**RULES For a typical dataset:**==
- $\rm{P}(\mu -\sigma <X<\mu +\sigma)=0.68$ 
- $\rm{P}(\mu -2\sigma <X<\mu +2\sigma)=0.95$ 
- $\rm{P}(\mu -3\sigma <X<\mu +3\sigma)=0.997$ 
	- i.e. ![[Screenshot 2024-08-12 at 8.32.35 PM.png|400]] 

- JUST REMEMBER THAT YOU MAY NEED TO ADD ON
	- I.e. $\rm{P}(\textrm{chocolates }>37)=0.95+\rm{P}(\textrm{more than }2\sigma)$ for $X\sim N(43,3^2)$ even if its within the 95% range
		- Because its still greater than 37 even if its above that range
		- 5% remaining -> distributed symetrically (2.5% per side)
		- Answer = $0.975$ 

**Using a calculator:**
- Normal cumulative distribution function - (Normal CDF) 
- Manually enter large/small numbers
	- I.e. $10^{99}$ 
- **Inverse normal option:**
	- use the calculator to find values of the cumulative distribution function of the normal distribution. (find values to plug in that give desired probability)
	- I.e. Let $X\sim N(2.2,0.5^2)$. Find the value of $b$ such that $\rm{P}(X<b)=0.72$.
	- Set Tail:
		- **LEFT** - if $X<b$ 
		- **RIGHT** - if $X>b$ 
	- ==FOR MY CALCULATOR==
		- Enter the area TO THE LEFT of the value that you are attempting to calculate (area less than the value we are trying to find)



# References

