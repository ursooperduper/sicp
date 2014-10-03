# SICP Exercise 1.3

## Exercise
Define a procedure that takes three numbers as arguments and returns the sum of the squares f the two larger numbers.

## Solution

```lisp
(define (square x)
  (* x x))

(define (sum-of-squares x y)
  (+ (square x) (square y)))

(define (compare x y z)
  (if (> x y)
    (if (> y z) (sum-of-squares x y) (sum-of-squares x z))
    (if (> x z) (sum-of-squares x y) (sum-of-squares y z))))
```
