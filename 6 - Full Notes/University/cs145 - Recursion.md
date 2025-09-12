2025-09-09 11:09

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 
[[dsa]] 


_______
# cs145 - Recursion

**Recursion:** when something is defined in terms of a smaller version of itself 
- Enables us to do things repeatedly 
- **Base case(s):** the smallest case(s) to define the object/function
- **Recursive case(s):** the way(s) to describe the object/function in terms of smaller similar objects or functions

**3 Key Questions:** 
1. What to do in the base case?
2. What to do with the current value?
3. How to combine the two with the recursive call?

**Induction vs Recursion:** 
- ![[Screenshot 2025-09-11 at 10.55.07 AM.png|300]]  
- Induction goes forward (assume base case and prove n=k+1)
- Recursion goes backwards (start from n=k) and then reverse until base case

**`check-expect`:** call before function definition in order to make test cases
- `(check-expect expr val)` 
	- Use for **tests/examples** in program + for assignments
		- **Examples:** very simple cases (put before function)
			- For recursive functions → one base case example + one recursive case example
		- **Tests:** more advanced cases + edge cases (put after function)
- I.e. 
```
check-expect (square 3) 9)
(check-expect (square 4) 16)
```
- Should output “All tests passed!” if done properly

**Example:** Summing from 1 to N (natural numbers)
- `1+2+...+N = (1+2+...+(N-1))+N` 
	- `S(n)=S(n-1)+n` 
- *Base case* → `0` if `n=0`
- *Recursive case* → else `n+s(n-1)` if `n>0` 
```js
(define (sumto N)
  (cond (
         (zero? N) 0)
        (else (+ N (sumto (sub1 N))))
        ))
```




# References

