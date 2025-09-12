2025-09-11 11:09

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - Efficiency Examples

**Example:**
![[Screenshot 2025-09-11 at 10.45.05 AM.png]]

| N   | (sumto N)    | (sumto-steps N)    | (sumto-size N)    |
| --- | ------------ | ------------------ | ----------------- |
| 0   | 0            | 3                  | 5                 |
| 1   | 1            | 8                  | 6                 |
| 2   | 3            | 13                 | 7                 |
| 3   | 6            | 18                 | 8                 |
| k   | k+sumto(k-1) | 5+sumto-steps(k-1) | 1+sumto-size(k-1) |
|     | k(k+1)/2     | 3+5k               | 5+k               |
- Add 5 to steps because there are 5 opening brackets for each function call
- Add 1 to size because you add 1 open bracket plus each time you recurse

**Example:** 
![[Screenshot 2025-09-11 at 10.46.44 AM.png]] 

| N   | (foo N) | (foo-steps N) |
| --- | ------- | ------------- |
| 0   | 1       | 3             |
| 9   | 1       | 3             |
| 10  | 2       | 8             |
| 20  | 2       | 8             |
| 99  | 2       | 8             |
| 100 | 3       | 13            |
|     |         |               |
- Counts amount of digits 
	- Floor of log base 10 + 1
- Steps is proportional to floor of log base 10
- Can prove what it does with the quotient
- *NOTE* → SIZE OF OUTPUT IS NOT ALWAYS EQUAL TO NUMBER OF STEPS
- For memory → count all brackets even if if statement doesn’t go through second part/first part

**Example:** Fibonacci numbers
![[Screenshot 2025-09-11 at 11.01.56 AM.png]] 

| N   | (fib N) | (fib-steps N) |
| --- | ------- | ------------- |
| 0   | 0       | 3             |
| 1   | 1       | 5             |
| 2   | 1       | 17            |
| 3   | 2       | 31            |
- Is very inefficient (time complexity - num of steps - is high)
	- Exponential




# References

