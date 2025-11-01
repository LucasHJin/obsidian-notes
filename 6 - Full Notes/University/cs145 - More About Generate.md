2025-10-31 10:34

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - More About Generate

Relates to [[generate|cs145 - Infinite Sequences]] 
- The function is sort of like storing memory → means you can mutate variables (kindof)

**Racket-ε**: version of racket with only 4 parts:
- Expression is either:
	- `num` 
	- `id` 
	- `‘(* exp exp)` (quoted list where quote propogates through)
	- `’(+ exp exp)` 
- Program is either:
	- `empty` 
	- `(cons exp pgm)` 
	- `(cons (define id val) pgm)` 
	- `(cons '(set id val) pgm)` 

**Example:** `'((define x 3) (+ x (+ 1 1)) (set x 7) x)` 
- This is a racket epsilon program
- Evaluation:

| stack                    | varlst     | res     |
| ------------------------ | ---------- | ------- |
| `(+ x (+ 1 1))`          | `’((x 3))` | `empty` |
| `x, (+ x (+ 1 1))`       | `’((x 3))` | `empty` |
| `3, (+ x (+ 1 1))`       | `’((x 3))` | `empty` |
| `(+ 3 (+ 1 1))`          | `’((x 3))` | `empty` |
| `(+ 1 1), (+ 3 (+ 1 1))` | `’((x 3))` | `empty` |
| `2, (+ 3 (+ 1 1))`       | `’((x 3))` | `empty` |
| `(+ 3 2)`                | `’((x 3))` | `empty` |
| `5`                      | `’((x 3))` | `empty` |
| …                        | …          | …       |
- Set 7 → just changes x 3 to x 7

*Note:* when working with generate, use it local to make it more clear:
```
(local ((define program (first state))
                                    (define stack (second state))
                                    (define varlst (third state))
                                    (define res (fourth state))
                                    (define currins (first program))
                                    (define currexp (if (empty? stack) "should never happen" (first stack))))
```




# References

