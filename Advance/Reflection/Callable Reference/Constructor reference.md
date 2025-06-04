:: can also convert constructors into lambdas.

Let’s say you have a class like this:

```kotlin
class User(val name: String)
```
Now imagine you're using a factory function that expects a lambda to create an instance of User. For example:

```kotlin
fun createUser(name: String, factory: (String) -> User): User {
    return factory(name)
}
```
If you try passing the constructor directly:

```kotlin
createUser("Sanskar", User) // ❌ Error: type mismatch
```
This won’t work — because the constructor is not a lambda.

But guess what? You can convert that constructor into a lambda using the :: operator:

```kotlin
createUser("Sanskar", ::User) // ✅ works perfectly!
```
::User is now a reference to the constructor, and it behaves just like a lambda of type (String) -> User.

In short:
Just like ::functionName turns a function into a lambda,
::ClassName turns a constructor into a lambda.
