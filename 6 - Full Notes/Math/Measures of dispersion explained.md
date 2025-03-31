2024-08-09 10:30

Status:


Tags:
[[math]]
[[statistics]]
[[school]]



___________________________________________________________________________
# Measures of dispersion explained

**Dispersion:** A general term for a measure of spread in a set of data.
- How much data is spread out or clustered together
	- Useful for when [[Measures of central tendency explained]] are the same or close but the data itself isn't
		- Set A: {3, 4, 5, 13, 13, 14, 18, 21, 23, 25, 26}
		  Set B: {3, 12, 13, 13, 13, 14, 15, 16, 16, 24, 26}
		- Mean, median, mode, range all the same
		- ![[Screenshot 2024-08-09 at 1.51.20 PM.png|400]] 


**Types:**
- **Range:** maximum-minimum
	- Not very useful
- **IQR** ($Q_3-Q_1$): distance between the first and third quartiles (middle 50% of the data)
- **Variance** ($\sigma^2$): A measure used to describe the spread of data within a population. It is the square of the standard deviation.
	- Higher value = more spread out
	- ==Uses GDC==
	- $\sigma ^2=\dfrac{\sum_{i=1}^{k}f_i(x_i-\mu)^2}{n}$ 
		- $f$ is frequency of data
		- $x$ is data
		- $\mu$ is mean
		- $n$ is total data
		- $k$ is amount of classes
	- $\sigma^2=\dfrac{\sum_{i=1}^{k}f_ix_i^2}{n}-\mu ^2$ 
- **Standard deviation** ($\sigma$): A measure used to describe the spread of data within a population. It is the square root of the variance.
	- Higher value = more spread out
	- ==Uses GDC==
	- $\sigma=\sqrt{\dfrac{\sum_{i=1}^{k}f_i(x_i-\mu)^2}{n}}$ 

**Data can then be summarized with:**
- Mean ± Standard deviation
	- I.e. Set A: $15\pm 8$ 

# References

