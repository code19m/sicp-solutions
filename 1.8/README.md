### **Exercise 1.8:** Newton’s method for cube roots is based on the fact that if y is an approximation to the cube root of x , then a better approximation is given by the value

---
## Solution

```scheme
; lang: scheme
(define (cube x) (* x x x))

(define (good-enough? previous-guess guess)
  (< (abs (/ (- guess previous-guess) guess)) 0.000000000001))

(define (cube-root-iter guess x)
  (if (good-enough? (improve guess x) guess)
      guess
      (cube-root-iter (improve guess x) x)))

(define (improve guess x)
  (/ (+ (/ x (* guess guess)) (* 2 guess)) 3))


(define (cube-root x)
  (cube-root-iter 1.0 x))

(cube-root 8)
```