:: converts a Kotlin function into a lambda.

Let's say you have a function that looks like this:
```
fun printSquare(a: Int) = println(a * 2)
```
And you have a class that takes a lambda as a 2nd argument:
```
class MyClass(var someOtherVar: Any, var printSquare: (Int) -> Unit) {
        
    fun doTheSquare(i: Int) {
        printSquare(i)
    }
}
```
How do you pass the printSquare function into MyClass? If you try the following, it wont work:
```
MyClass("someObject", printSquare) //printSquare is not a LAMBDA, it's a function so it gives compile error of wrong argument
```
So how do we CONVERT printSquare into a lambda so we can pass it around? Use the :: notation.

```
MyClass("someObject",::printSquare) //now compiler does not complain since it's expecting a lambda and we have indeed converted the `printSquare` FUNCTION into a LAMBDA.
```
Also, please note that this is implied... meaning this::printSquare is the same as ::printSquare. So if the printSquare function was in another class, like a Presenter, then you could convert it to lambda like this:

Presenter::printSquare
