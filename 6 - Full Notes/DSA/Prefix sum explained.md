2025-08-17 12:23

Status:


Tags:
[[dsa]]  
[[lc]] 


_______
# Prefix sum explained

Technique where you preprocess an array so you can quickly answer range sum queries in constant time (O(1))
- Store sum of values from beginning to the current index of the array (can exclude if necessary)
	- Can also be for products, etc.
- Then → `sum(i,j)=prefix[j]-prefix[i-1]` 
	- Takes O(1) after O(n) preprocessing

**Use cases:** 
- Range sum queries
- Counting frequencies → convert to a 0/1 array and compute prefix sum
- Sliding window/subarray sums → can compute once per window
- Difference arrays
- Finding subarrays with a certain sum k → use prefix sum + hashmap

# References

