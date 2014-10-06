# SICP Exercise 1.6

## Exercise

Alyssa P. Hacker doesn't see why `if` needs to be provided as a special form. "Why can't I just define it as an ordinary procedure in terms of `cond`?" she asks. Alyssa's friend Eva Lu Ator claims this can indeed be done, and she defines a new version of `if`:

```lisp
(define (new-if predicate then-clause else-clause)
  (cond (predicate then-clause)
    (else else-clause)))
```

Eva demonstrates the program for Alyssa:

```lisp
(new-if (= 2 3) 0 5)
5

(new-if (= 1 1) 0 5)
0
```

Delighted, Alyssa uses `new-if` to rewrite the square-root program:

```lisp
(define (sqrt-iter guess x)
  (new-if (good-enough? guess x)
    guess
    (sqrt-iter (improve guess x) x)))
```

What happens when Alyssa attempts to use this to computer square roots? Explain.

## Solution

Alyssa's program will fail because it exceeds the interpreter's maximum recursion depth.

The new-if version uses applicative evaluation (meaning the operands are always evaluted), whereas 'if' uses normal order evaluaton (predicates evaluate before operands). So the predicate decides which operand gets evaluated.

;In new-if sqrt-iter is called recursively despite good-enough being evaluated to true because the operands are being evaluated.
