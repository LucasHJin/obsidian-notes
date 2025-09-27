2025-09-26 10:41

Status:


Tags:
[[uni]] 
[[cs]] 
[[cs145]] 


_______
# cs145 - Heaps

**Heap:** either
- Empty OR
- `(make-node left right key)` where left and right are heaps and key is greater than any key in the left/right subtrees
	- Max value on top
	- No other specific ordering + keys = unique

**Use cases:** 
- Sorting

**Insertion:** 
- If you have large values → replace value it is greater than and then insert the replaced value
	- Recursively insert into the tree with less nodes (keeps it looking like a heap instead of just a single line)

```js
(define-struct node (l r k))

(define (insert1 h n)
  (cond ((empty? h) (make-node empty empty n))
        ((> n (node-k h)) (make-node h empty n))
        (else (make-node (insert (node-l h) n) (node-r h) (node-k h)))))

(define (insert h n)
  (cond ((empty? h) (make-node empty empty n))
        ((> n (node-k h)) (if (< (size (node-l h)) (size (node-r h)))
                              (make-node (insert (node-l h) (node-k h)) (node-r h) n)
                              (make-node (node-l h) (insert (node-r h) (node-k h)) n)))
        (else (if (< (size (node-l h)) (size (node-r h)))
                  (make-node (insert (node-l h) n) (node-r h) (node-k h))
                  (make-node (node-l h) (insert (node-r h) n) (node-k h))))
        ))

(define (size h)
  (cond ((empty? h) 0)
        (else (+ 1 (size (node-l h)) (size (node-r h))))))

(define (rem h)
  (cond ((and (empty? (node-l h)) (empty? (node-r h))) empty)
        ((empty? (node-r h)) (make-node (rem (node-l h)) empty (node-k (node-l h))))
        ((empty? (node-l h)) (make-node empty (rem (node-r h)) (node-k (node-r h))))
        ((< (node-k (node-l h)) (node-k (node-r h))) (make-node (node-l h) (rem (node-r  h)) (node-k (node-r h))))
        (else (make-node (rem (node-l h)) (node-r h) (node-k (node-l h))))
        ))

(define (lst->heap lst)
  (cond ((empty? lst) empty)
        (else (insert (lst->heap (rest lst)) (first lst)))))

(define (heap->lst h)
  (cond ((empty? h) empty)
        (else (cons (node-k h) (heap->lst (rem h))))))

(define (heapsort lst)
  (heap->lst (lst->heap lst)))
```

# References

