2025-08-16 15:46

Status:


Tags:
[[ls]] 
[[dsa]] 


_______
# Sliding window explained

**How it works:** extension of the [[Two pointers explained|two pointers]] pattern except instead of tracking 2 positions → you manage a range of values (window)
- Slide window across data structure to inspect different parts of it
- **General pattern:** 
	- Look at a subset of the data
	- Adjust the window as needed
	- Never revisit elements
- Reduces time complexity to O(n) instead of O(n^2)
- **Method 1:** Fixed window
	- Used when problem gives specific window size
		- ![[Screenshot 2025-08-16 at 3.50.27 PM.png]] 
	- Code template:
		- ![[Screenshot 2025-08-16 at 3.51.36 PM.png]] 
			- Remove the old element, add a new one → calculate the new desired value (keep it always length `window_size`) 
- **Method 2:** Dynamic window (more powerful)
	- Used when window size isn’t fixed
		- Want largest, smallest, optimal range that satisfies a condition
		- ![[Screenshot 2025-08-16 at 3.53.54 PM.png]] 
	- Expand the window to include more elements until condition is violated and then shrink again until it’s satisfied again
		- ![[Screenshot 2025-08-16 at 3.54.46 PM.png]] 

**For problems with:** 
- Contiguous segments (substring,  subarray, group of consecutive elements)

**Examples:** 
- Maximum sum for subarray of length k → build initial window and find sum
	- Each time → slide window and compare new sum (only need to add/remove 1 number each)
- Longest substring without repeating characters → keep increasing sliding window until hashmap has more than 1 and then use a while loop to shrink window until no repeating characters again

# References

