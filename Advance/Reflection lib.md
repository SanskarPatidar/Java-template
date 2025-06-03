Here’s a comparison of **Reflection** in **Java**, **Kotlin**, and **C++ (syntax only)** in your preferred format:

---

### 🪞 Reflection (Introspecting Classes, Methods, Fields at Runtime)

* **Java:** Use the `java.lang.reflect` package to access class metadata at runtime.
* **Kotlin:** Use `::class`, `KClass`, and `javaClass`; supports full reflection via `kotlin.reflect`.
* **C++:** ❌ No built-in reflection; use type traits or third-party libraries.

---

### 🔍 Getting Class Metadata

```java
Class<?> cls = MyClass.class;
System.out.println(cls.getName());
```

```kotlin
val cls = MyClass::class
println(cls.simpleName)
```

---

### 🧪 Creating Object Dynamically

```java
MyClass obj = (MyClass) Class.forName("MyClass").newInstance();
```

```kotlin
val ctor = MyClass::class.constructors.first()
val obj = ctor.call()
```

---

### 🔧 Accessing Methods/Fields

```java
Method m = cls.getDeclaredMethod("sayHello");
m.invoke(obj);  // invoke method
```

```kotlin
val method = cls.members.first { it.name == "sayHello" }
method.call(obj)
```

---

### 🛠 C++ Syntax Only (No Example)

```cpp
// No built-in reflection; use typeid(obj).name() or templates
typeid(obj).name();
```

---

Would you like to continue with **reflection use cases in Spring Boot**, **modifying private fields**, or **annotations with reflection**?
