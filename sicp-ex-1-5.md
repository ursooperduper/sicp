# SICP Exercise 1.5

## Exercise

Ben Bitdiddle has invented a test to determine whether the interpreter he is faced with is using applicative-order evaluation or normal-order evaluation. He defines the following two procedures:

```lisp
(define (p) (p))

(define (test x y)
  (if (= x 0) 0 y))
```

He evaluates the expression

```lisp
(test 0 (p))
```

What behavior will Ben observe with an interpreter that uses applicative-order evaluation? What behavior will he observe with an interpreter that uses normal-order evaluation? Explain your answer. (Assume that the evaluation rule for the special form `if` is the same whether the interpreter is using normal or applicative order: The predicate expression is evaluated first, and the result determines whether to evaluate the consequent or the alternative expression.)

## Solution

For an interpreter that uses applicative-order evaluation, Ben's test will never end because (p) keeps evaluating - infinite recursion. In normal-order evaluation, the evaluation will execute one step at a time (resulting in 0).
