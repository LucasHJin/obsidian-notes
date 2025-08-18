---
difficulty: medium
review: true
---
2025-08-16 20:36

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(n)
**Space complexity:** O(n)
_______
# LC - Top K Frequent Elements

**Preliminary notes:** 
- Make a dictionary and then sort the dictionary based on the values in kv pairs
	- Then return the first k values
- BUT → this requires O(nlog n) for sorting

**Finished notes:** 
- Use a [[Bucket sort explained|bucket sort]] (bucket items by frequency)
	- Initially → just count up the number of each number and store that amount as the value under the number as the key
	- Then, create a 2d list where you use the amount as the index and append the number to the list
		- Guaranteed the max index is equal to the amount of items
	- Then just go through the list in reverse until you have k elements
- *Note* → can do something similar with min heap but it’s O(logk) insertion instead of O(1) so its slower

# References

