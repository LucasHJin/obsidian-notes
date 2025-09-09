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

