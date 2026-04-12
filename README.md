## 🎯 ফরম্যাট স্পেসিফায়ার কী?

ফরম্যাট স্পেসিফায়ার হলো **বিশেষ কোড** যা জাভাতে আউটপুট ফরম্যাট করার জন্য ব্যবহার করা হয়। এগুলো `printf()` বা `String.format()` মেথড ব্যবহার করার সময় ডেটা কিভাবে দেখাবে তা কন্ট্রোল করে।

## 📊 Commonly Used Format Specifiers

| Specifier | Data Type | Example                                              | Output                           |
| --------- | --------- | ---------------------------------------------------- | -------------------------------- |
| `%d`      | `int`     | `System.out.printf("Integer value: %d", 25);`        | `Integer value: 25`              |
| `%f`      | `double`  | `System.out.printf("Floating value: %f", 10.5);`     | `Floating value: 10.500000`      |
| `%c`      | `char`    | `System.out.printf("Character value: %c", 'A');`     | `Character value: A`             |
| `%s`      | `String`  | `System.out.printf("String value: %s", "Java");`     | `String value: Java`             |
| `%b`      | `boolean` | `System.out.printf("Boolean value: %b", true);`      | `Boolean value: true`            |
| `%e`      | `double`  | `System.out.printf("Scientific value: %e", 123.45);` | `Scientific value: 1.234500e+02` |
| `%x`      | `int`     | `System.out.printf("Hexadecimal value: %x", 255);`   | `Hexadecimal value: ff`          |
| `%%`      | -         | `System.out.printf("Percent sign: %%");`             | `Percent sign: %`                |

## 🔧 How to Use Format Specifiers
### Method 1: Using `printf()` Method

```java
public class Main {
    public static void main(String[] args) {
        String name = "Rahim";
        int age = 25;
        double price = 99.99;
        
        System.out.printf("Name: %s, Age: %d, Price: %.2f", name, age, price);
    }
}
```

**Output:**
```
Name: Rahim, Age: 25, Price: 99.99
```

