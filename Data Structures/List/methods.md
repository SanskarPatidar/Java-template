![image](https://github.com/user-attachments/assets/0a7c3b78-4e8c-46ac-983b-777e4b321428)
![image](https://github.com/user-attachments/assets/090ded72-2ede-418e-8e69-af6642606587)
```java
import java.util.*;
import java.util.stream.*;

public class Demo {
    public static void main(String[] args) {
        List<Integer> nums = Arrays.asList(1, 2, 3, 4, 5);

        // .map: square each number
        List<Integer> squares = nums.stream()
                                    .map(n -> n * n)
                                    .collect(Collectors.toList());

        // .filter: keep only even numbers
        List<Integer> evens = nums.stream()
                                  .filter(n -> n % 2 == 0)
                                  .collect(Collectors.toList());

        System.out.println("Squares: " + squares);
        System.out.println("Evens: " + evens);
    }
}
```
```kotlin
fun main() {
    val nums = listOf(1, 2, 3, 4, 5)

    // .map: square each number
    val squares = nums.map { it * it }

    // .filter: keep only even numbers
    val evens = nums.filter { it % 2 == 0 }

    println("Squares: $squares")
    println("Evens: $evens")
}

```

![image](https://github.com/user-attachments/assets/b64c23f4-6e32-4778-a5af-44419b398b5b)
![image](https://github.com/user-attachments/assets/024b20e5-d7c4-4587-b1f9-5169ded3a89b)

