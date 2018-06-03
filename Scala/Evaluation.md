
Actually, operators are just methods with symbolic names:

```
3 + 2 == 3.+(2)
```

#### methods
>Function parameters come with their type, which is given after a colon
```
def power(x: Double, y: Int): Double = square(x) + square(y)
```



#### EVALUATION

##### THE SUBSTITUTION MODEL

>This scheme of expression evaluation is called the substitution model.

>The idea underlying this model is that all evaluation does is reduce an expression to a value.

>It can be applied to all expressions, as long as they have no side effects.

>The substitution model is formalized in the λ-calculus, which gives a foundation for functional programming.

TERMINATION

>Does every expression reduce to a value (in a finite number of steps)?

>No. Here is a counter-example:

```
def loop: Int = loop

loop
```

##### VALUE DEFINITIONS AND TERMINATION

>The difference between val and def becomes apparent when the right hand side does not terminate. Given
```
def loop: Int = loop
```
A definition
```
def x = loop
```
is OK, but a value
```
val x = loop
```
will lead to an infinite loop.




#### CALL-BY-NAME (CBN)AND CALL-BY-VALUE (DBV)
>The first evaluation strategy is known as call-by-value, the second is is known as call-by-name.

Both strategies reduce to the same final values as long as

- the reduced expression consists of pure functions, and
- both evaluations terminate.


>- Call-by-value has the advantage that it evaluates every function argument only once.
>- Call-by-name has the advantage that a function argument is not evaluated if the corresponding parameter is unused in the evaluation of the function body.

Scala normally uses call-by-value.

e.g.  
note the **=>** with CBN

```
def callByName[T](block: => T) = {
    for( i<-0 until 10){
        println(block)
    }
}
def callByValue[T](block: T) = {
    for( i<-0 until 10){
        println(block)
    }
}
```
