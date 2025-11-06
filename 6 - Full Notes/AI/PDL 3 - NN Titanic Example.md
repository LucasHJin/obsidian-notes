2025-11-05 11:24

Status:


Tags:
[[cs]] 
[[ai]] 
[[ml]] 
[[dl]] 
[[rl]] 



_______
# PDL 3 - NN Titanic Example

**Cleaning data:** want everything to be between 0 and 1 normally
- Need to convert non-numbers to numbers to be multiplied (or if it’s not continuous)
	- **Binary categorical variables:** 1 / 0 depending on either A is true or B is true
- **Normalizing data:** divide values by max value (for continuous values like age / fare)
	- So that they’re all between 0 and 1 (makes sure all parameters train at the same approx same speed) (**Dummy variables**)
	- Or take `log` for more extreme differences
- *Note* → FastAI does all of this for you
- *Note* → dummy variables only need `n-1` columns for `n` categorical categories
	- Because the computer can infer that if it’s not A then it must be B

**Trick:** add a column of 1 containing number 1 every time
- That becomes your constant term (`b`)

**Matrix multiplication:** 
- Parameters shouldn’t match data in columns
- Flip it so that each of the rows are the columns of the data and then each column is a new set of parameters

# References

