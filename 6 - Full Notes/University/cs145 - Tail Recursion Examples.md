2025-09-16 10:24

Status:


Tags:
[[cs]] 
[[cs145]] 
[[uni]] 


_______
# cs145 - Tail Recursion Examples

**Example (sumto tail recursion):**
```js
(define (sumto n)
  (sumto-help n 0))

(define (sumto-help n accum)
  (if (zero? n) accum (sumto-help (- n 1) (+ accum n))))
```

| Count | Fxn               |
| ----- | ----------------- |
| 1     | (sumto 4)         |
| 2     | (sumto-help 4 0)  |
| 3     | (sumto-help 3 4)  |
| 4     | (sumto-help 2 7)  |
| 5     | (sumto-help 1 9)  |
| 6     | (sumto-help 0 10) |
| 7     | 10                |

**Example (pow):** 
```js
(define (pow b n)
  (if (zero? n) 1
      (* b (pow b (sub1 n)))))
```

| N   | (pow 2 N) | (pow-steps 2 N) |
| --- | --------- | --------------- |
| 0   | 1         | 3               |
| 1   | 2         | 9               |
| 2   | 4         | 15              |
| 3   | 8         | 21              |
| 4   | 16        | 27              |
```js
(define (pow2 b n)
  (if (zero? n) 1
      (if (odd? n)
          (* b (pow b (sub1 n)))
          (* (pow b (quotient n 2)) (pow b (quotient n 2))))))
// If odd split in 2 (takes more steps cause you call 2 functions)
```
| N   | (pow 2 N) | (pow-steps 2 N) |
| --- | --------- | --------------- |
| 0   | 1         | 3               |
| 1   | 2         | 10              |
| 2   | 4         | 29              |
| 3   | 8         | 36              |
| 4   | 16        | 67              |
```js
(define (pow-help t) (* t t))

(define (pow3 b n)
  (if (zero? n) 1
      (if (odd? n)
          (* b (pow3 b (sub1 n)))
          (pow-help (pow3 b (quotient n 2)))))) 
          // Instead of calling pow3 twice
```

| N   | (pow 2 N) | (pow-steps 2 N) |
| --- | --------- | --------------- |
| 0   | 1         | 3               |
| 1   | 2         | 10              |
| 2   | 4         | 19              |
| 3   | 8         | 25              |
| 4   | 16        | 27              |
- Increases by a logarithm of the input size (faster for bigger N)
# References

