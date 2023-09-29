### **Exercise 1.4:** Observe that our model of evaluation allows for combinations whose operators are compound expres- sions. Use this observation to describe the behavior of the following procedure:
```scheme
(define (a-plus-abs-b a b) 
  ((if (> b 0) + -) a b))
```

## Solution
If b is strictly a positive number, the operator expression (if (> b 0) + -) will evaluate to + the result will be a + b.

If all other cases, the result will be a − b.

In other words, this function compute a + | b |.