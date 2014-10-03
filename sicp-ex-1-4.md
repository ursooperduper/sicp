# SICP Exercise 1.4

## Exercise:
Observe that our model of evaluation allows for combinations whose operators are compound expressions. Use this observation to describe the behavior of the following procedure:

```lisp
(define (a-plus-abs-b a b)
  ((if (> b 0) + -) a b))
```

## Solution:
