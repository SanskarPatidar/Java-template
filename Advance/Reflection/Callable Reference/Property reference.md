Yes, :: works on properties too — but only in Kotlin, not Java.

Let’s say you have a simple property:

```kotlin
val title = "Kotlin is awesome"
```
And now you want to refer to it like an object. You can do:

```kotlin
val titleRef = ::title
println(titleRef.get()) // prints "Kotlin is awesome"
```
So what happened here?

::title is a property reference

titleRef is now a KProperty0<String>

You can .get() its value at any time

This works great for:

1. Reflection

2. Passing around property getters

3. Observable or delegated properties

If the property was inside a class:

```kotlin
class Book(val name: String)

val ref = Book::name
println(ref.get(Book("Ramayana"))) // prints "Ramayana"
```
You're essentially saying:
“Hey Kotlin, give me a reference to the name property of Book, and I’ll use it like a lambda that pulls out the value.”
