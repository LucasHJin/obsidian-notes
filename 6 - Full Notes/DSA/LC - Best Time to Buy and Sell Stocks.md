---
difficulty: easy
review:
---
2025-08-26 11:28

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(1)
_______
# LC - Best Time to Buy and Sell Stocks

**Preliminary notes:** 
- Use a [[Sliding window explained|sliding window]] approach
	- Dynamic window
	- If the right pointer is bigger → calc new profit 
	- Else → set left equal to right (if `prices[l]>=prices[r]`) 
		- Guarantees that the left pointer always tracks the minimum (because it will keep going until it reaches the minimum)
		- Basically right keeps traversing until it reaches the very lowest (and l becomes it) but it also calculates any time a profit is possible
	- Then increase right by 1

**Finished notes:** 
- 

# References

