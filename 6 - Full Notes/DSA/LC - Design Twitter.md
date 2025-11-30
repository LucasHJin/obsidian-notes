---
difficulty: medium
review: true
---
2025-11-29 15:23

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(nlogn) for getNewsFeed
**Space complexity:** O((N * m) + (N * M) + n)
_______
# LC - Design Twitter

**Preliminary notes:** 
- Use a dictionary to keep track of each person and who they follow
	- Use a set inside this → faster lookup
- Use a heap to keep track of posts in order of most recent (top 10)
	- Use a counter → use this to assign a time posted for each post id
	- Use a minheap → means you need to subtract from the counter each time for newer values

**Finished notes:** 
- Logic is similar to above:
	- Keep track of follows with a dict(set)
	- BUT → don’t use a heap for each individual person’s posts
		- Use a dict of lists (append at the end)
	- Just use a heap when combining for getnewsfeed (newer tweets are stored at the end because of append)
		- Use [[LC - Merge K Sorted Lists]] strategy
		- Have a heap to temp keep track of most recent post from each user + a final answer list
		- Pop from the heap the top value, add in the next post from this person (index - 1) and continue this until you have 10 answers
- *Note* → make sure you follow yourself so that logic is repeated (need this because they can’t follow themselves in the testcases)
- *Note* → not actually more time efficient for `n=10` 
	- But if it was just n → would be more time efficient
 

# References

