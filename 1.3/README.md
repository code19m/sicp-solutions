### **Exercise 1.3:** Define a procedure that takes three numbers as arguments and returns the sum of the squares of the two larger numbers.
___
## Solution

```scheme
; lang: scheme

(define (squares_sum_largest a b c)
  (cond
    ((<= a (min b c)) (squares_sum b c))
    ((<= b (min a c)) (squares_sum a c))
    (else (squares_sum a b))
  )
)

(define (squares_sum a b)
  (+ (* a a)
     (* b b)
  )
)

(define (min a b)
  (if (< a b)
    a
    b
  )
)
```

```python
# lang: python

def squares_sum_largest(a, b, c):
    if a <= min(b, c):
        return squares_sum(b, c)
    if b <= min(a, c):
        return squares_sum(a, c)
    return squares_sum(a, b)

def squares_sum(a, b):
    return (a * a) + (b * b)
```

```go
// lang: go

func SquaresSumLargest(a, b, c int64) int64 {
	if a < b && a < c {
		return squaresSum(b, c)
	} else if b < a && b < c {
		return squaresSum(a, c)
	} else {
		return squaresSum(a, b)
	}
}

func squaresSum(a, b int64) int64 {
	return a*a + b*b
}
```