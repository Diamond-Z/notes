
#### Boolen espressions

```
true  false      // Constants
!b               // Negation
b && b           // Conjunction
b || b           // Disjunction
```



```
def sqrtIter(guess: Double, x: Double): Double =
  if (isGoodEnough(guess, x)) guess
  else sqrtIter(improve(guess, x), x)

def improve(guess: Double, x: Double) =
    (guess + x / guess) / 2

def isGoodEnough(guess: Double, x: Double) =
    abs(guess * guess - x) < 0.001
```

You have seen simple elements of functional programing in Scala.


- arithmetic and boolean expressions
- conditional expressions if-else
- functions with recursion
