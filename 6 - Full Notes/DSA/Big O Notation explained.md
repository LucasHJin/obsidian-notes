2025-08-16 15:12

Status:


Tags:
[[ls]] 
[[dsa]] 


_______
# Big O Notation explained

A way to measure the time and space complexity of an algorithm
- Provides upper bound for complexity in worst case scenario

**O(1):** Time complexity stays same no matter how many elements
- I.e. checking if a value exists in a set or accessing a value in an array
**O(logn):** Problem gets divided in half each time
- I.e. binary search
**O(n):** Going through each item once
- Associated with loops and traversing lists
**O(nlogn):** Almost always related to ==sorting== 
- Includes default sorting languages
**O(n^2):** Almost always associated with nested loops
- Brute force → ALMOST ALWAYS BAD

**Rule of thumb:** 
- Input size up to $10^5$ → need **O(nlogn)** or smaller
- Input size up to $10^4$ → need **O(n^2)** or smaller




# References

