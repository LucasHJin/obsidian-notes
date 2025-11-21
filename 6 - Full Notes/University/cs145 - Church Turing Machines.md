2025-11-21 10:36

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - Church Turing Machines

**Turing machine:** a game played on an infinite strip of 1’s and 0’s (can have more than this → alphabet)
- **State:** `S={S0, S1}` 
	- `S0 = (R, T, S0) on T`
		- `S0 = (L, T, S1) on F` (move left, change false to true, change to S1)
		- F = do not halt
	- `S1 = ()` 
		- `S1 = ()` 
		- T = halt
- Finds first false to turn into true (add1) ^^
- If instead:
	- `S1 = (L, T, S2)` 
		- `S1 = (L, T, S2)` 
		- F
	- `S2 = () () T` 
	- Can add 2 trues



# References

