2024-08-08 20:27

Status:


Tags:
[[math]]
[[statistics]]
[[school]]


___________________________________________________________________________
# Box and whisker plot explained

**Box and whisker plot (box plot):** 
- Useful for illustrating 5-number summary
	- I.e. ![[Screenshot 2024-08-08 at 9.03.06 PM.png|400]] 
		- minimum = 12
		- $Q_1$ = 13
		- median = 16
		- $Q_3$ = 31
		- maximum = 33
- $Q_1$ and $Q_3$ are the ends of the box
	- Draw lines from them to minimum and maximum
		- Called '==whiskers=='
	- If same, don't draw line
- Summary:
	- 0-25% = whisker #1
	- 25-75% = box
	- 75-100% = whisker #2
	- ![[Screenshot 2024-08-08 at 9.42.08 PM.png|400]]

**Interpreting B&W plot:** 
- Useful for exploring spread of data over the range
	- I.e. if LH whisker is short -> first 25% of data is all close together
	- I.e. if RH whisker is long -> last 25% of data is spread out
- Middle 50% often used to find a range of typical results within a given scenario

**Distribution and skewing of mean:** 
- BW can show if the spread is:
	- **Normally distributed**
		- Continuous distribution of data where middle (mean, median, mode) is the highest part and decreases equally on each side
			- ==mean=median== 
			- ![[Screenshot 2024-08-08 at 9.45.35 PM.png]]
	- **Positively skewed**
		- Continuous distribution of data where most data is clustered together with a couple extremely high exceptions
			- ==mean>>median== 
			- ![[Screenshot 2024-08-08 at 9.47.12 PM.png]]
	- **Negatively skewed**
		- Continuous distribution of data where most data is clustered together with a couple extremely low exceptions
			- ==mean<<median== 
			- ![[Screenshot 2024-08-08 at 9.47.22 PM.png]]

**Outliers:** A particularly unusual value in a set of data in that it is much lower or much higher than the rest of the data.
- In mathematics:
	- $outlier<Q_1-1.5\cdot IQR$ 
	- $outlier>Q_3+1.5\cdot IQR$ 
- Need to be indicated on BW plot so that false conclusions are not made
	- Done with $*$, $x$, or $\cdot$ 
	- I.e. ![[Screenshot 2024-08-08 at 11.12.52 PM.png|400]]
		- Shows that the distribution is much more normal than one might think


# References

