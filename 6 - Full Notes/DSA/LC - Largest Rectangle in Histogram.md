---
difficulty: hard
review: true
---
2025-08-20 14:02

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(n)
_______
# LC - Largest Rectangle in Histogram

**Preliminary notes:** 
- Have a largest value and then a stack to keep track of smallest height + start index
	- Calculate the area compared to currrent each time
	- If the length version is bigger vs if the height version is bigger
**Finished notes:** 
- ABOVE IS WRONG
- Solution #1
	- For each bar, calculate the max area it can take up by extending to the left and right (to bars equal or greater than it)
		- Do this by using 2 loops → left to right and right to left
		- Add value to stack and while height at that index is bigger, pop it until a smaller one → that’s how far you can reach
			- Add it to another array for how far it can reach for that one
- Solution #2 - more efficient
	- OR → only extend to the right and pop values in the past if they are smaller than current height
		- Then backtrack to find start index
		- Have a stack → holds start index for each height + height itself

# References

