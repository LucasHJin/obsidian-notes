2025-08-16 15:29

Status:


Tags:
[[ls]] 
[[dsa]] 


_______
# Two pointers explained

Fundamental for solving problems involving linear structures
- I.e. [[Data structures explained|arrays, strings, linked lists]] 

**How it works:** use 2 indices/pointers move through a structure (one tracking start and one tracking end)
- To avoid nested loops
- **Method 1:** both pointers move in same direction
	- When you want to do a single pass but track a range (not single element)
	- Fast + slow 2 pointer setup → faster one moves 2 steps at a time
		- I.e. you can find the middle of something or if there is a cycle
- **Method 2:** pointers move towards each other from opposite ends
	- When:
		- the array is sorted and you are trying to find a pair/combination
		- comparing symmetric parts of a structure (palindrome)
		- avoiding nested loops when looking at pairs
	- Based on condition → move one towards the other 

**Useful:** 
- Reduces the number of iterations needed
- Tracks relationships between 2 places
- Avoids extra spaces (i.e. sets/maps)

**For problems with:** 
- Palindromes
- Reversals
- Merging sorted data
- “K” sized comparison

**Example:** 
- Valid palindrome → start on the two opposite ends and then check each time if they are the same
- Middle of linked list → make one going 2x the speed of the other and when it reaches the end, the first one has reached halfway
# References

