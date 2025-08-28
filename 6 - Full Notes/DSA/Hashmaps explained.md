2025-08-16 15:16

Status:


Tags:
[[ls]] 
[[dsa]] 


_______
# Hashmaps explained

**Hashmap:** way to store data using a key to find a value (i.e. a dictionary)
- Use custom indices instead of default numbers to access values
- *Lookup* → **O(1)** 
- *Insertion* → **O(1)** 
- GO TO STRUCTURE WHEN BRUTE FORCE FAILS
	-  I.e. finding a value that already exists → can remember instead of asking same question
- **General pattern:** use while you loop → one pass through
	- Store something
	- Look something up
	- Update/initialize values
- *Useful:* 
	- `enumerate` → gives both current index `i` and current value `num` 
	- `defaultdict` → every character starts with a count of 0

*Notes*:
- Sometimes, two keys might get same hash (points to slot in memory where value is stored)
	- Most languages have built in hashmap implementations that handle collisions
- **Keys must be hashable:** the keys must be immutable (unchanged)
	- Can be → numbers, strings, tuples
	- Cannot be → lists, dictionaries
- If you make a hashmap for alphabet using list:
	- **FIXED SIZE → comparison is O(1)** 



# References

