# SICP Exercise 1.4

## Exercise

Observe that our model of evaluation allows for combinations whose operators are compound expressions. Use this observation to describe the behavior of the following procedure:

```lisp
(define (a-plus-abs-b a b)
  ((if (> b 0) + -) a b))
```

## Solution

There is a function called `a-plus-abs-b` that evaluates based on two inputs, `a` and `b`.

First, check if `b` is greater than 0. If it is, add a + b. If the number is not greater than zero, we subtract a - b.
