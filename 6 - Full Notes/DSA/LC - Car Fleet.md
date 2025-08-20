---
difficulty: medium
review: true
---
2025-08-19 19:44

Status:


Tags:
[[lc]] 
[[dsa]] 

**Time complexity:** O(nlogn)
**Space complexity:** O(n)
_______
# LC - Car Fleet

**Preliminary notes:** 
- They become a fleet when $p_1+s_1*x=p_2+s_2*x$ → see if this happens before or at when they reach the target
	- Use a stack to keep track of number of fleets → add on if it becoms a new fleet
	- At the end → length of stack is answer
- Need to sort first → from farthest position to closest position
- Probably also better to calculate the amount of time → rather than get the value and then replugin
- This works because:
	- Even if there is a super fast one with a very low starting position (at the bottom of the array) → it will slow down grealty once it becomes a fleet with another car
		- So then it depends on that car’s time to become a fleet with other cars (which is already calculated)
		- I.e. doesn’t matter when the fast car reaches the slow car, irregardless it drives the same speed unless it reaches a even slower car

**Finished notes:** 
- Could have used a counter for number of fleets → instead of checking length of stack
- Also don’t need a stack → can just keep track of previous speed and current speed → start from index 1

# References

