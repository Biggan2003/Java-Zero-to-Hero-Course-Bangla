# Java-Zero-to-Hero-Course-Bangla


## 🎯🎯🎯 ফরম্যাট স্পেসিফায়ার কী?

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
------------
--------------
-------------




# 🎯🎯🎯 How to Get Input from the User

### 1. কেন ইনপুট দরকার? (Why Need Input?)
- ইনপুট ছাড়া প্রোগ্রাম → স্থির/অপরিবর্তনীয় (fixed/static)
- ইনপুট সহ প্রোগ্রাম → গতিশীল ও ইন্টারেক্টিভ (dynamic & interactive)
- উদাহরণ: ক্যালকুলেটরে ইউজারের কাছ থেকে দুটি সংখ্যা নিতে হয়
---
### 2. Scanner কী? (What is Scanner?)
- Scanner হলো Java-র বিল্ট-ইন একটি ক্লাস
- এটি কিবোর্ড থেকে ইনপুট পড়ে
- এটি `java.util` প্যাকেজের ভিতরে অবস্থিত
---
### 3. Steps to Take Input
#### Step 1: Import Scanner
```java
import java.util.Scanner;
```
#### Step 2: Create Scanner Object
```java
Scanner input = new Scanner(System.in);
```

#### Step 3: Read Input Using Methods

|Method|Purpose|Example|
|---|---|---|
|`nextInt()`|Read integer|`int x = input.nextInt();`|
|`nextDouble()`|Read double|`double d = input.nextDouble();`|
|`next()`|Read single word|`String s = input.next();`|
|`nextLine()`|Read full line|`String line = input.nextLine();`|
|`nextBoolean()`|Read boolean|`boolean b = input.nextBoolean();`|
|`next().charAt(0)`|Read character|`char c = input.next().charAt(0);`|

#### Step 4: Close Scanner (Good Practice)
```java
input.close();
```
### কেন `input.close()` ব্যবহার করবেন?

**১. মেমোরি লিক প্রতিরোধ করা (Prevent Memory Leak)**
- যখন আপনি Scanner খোলেন, এটি আপনার কম্পিউটারের মেমোরির কিছু জায়গা দখল করে নেয়
- `close()` না করলে সেই মেমোরি খালি হয় না
- প্রোগ্রাম শেষ হওয়ার পরও মেমোরি আটকে থাকতে পারে

**২. রিসোর্স লিক বন্ধ করা (Close Resource Leak)**
- Scanner শুধু মেমোরি না, এটি আপনার কিবোর্ড বা ফাইলের সাথে একটি "সংযোগ" তৈরি করে
- এই সংযোগ বন্ধ না করলে সিস্টেম ধীর হয়ে যেতে পারে
- অনেক প্রোগ্রাম একসাথে চালালে সমস্যা দেখা দেয়

**৩. ভালো প্রোগ্রামিং অভ্যাস (Good Programming Practice)**
- পেশাদার প্রোগ্রামাররা সবসময় খোলা রিসোর্স বন্ধ করেন
- এটি আপনার কোডকে "ক্লিন" ও "প্রফেশনাল" করে তোলে
- 
### 4. Complete Example
```java
import java.util.Scanner;

public class InputExample {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        
        System.out.print("Enter your name: ");
        String name = input.nextLine();
        
        System.out.print("Enter your age: ");
        int age = input.nextInt();
        
        System.out.print("Enter your CGPA: ");
        double gpa = input.nextDouble();
        
        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("CGPA: " + gpa);
        
        input.close();
    }
}
```

### 5. Common Problem & Solution
#### Problem: `nextLine()` gets skipped
**Wrong Code:**
```java
System.out.print("Enter age: ");
int age = input.nextInt();
System.out.print("Enter name: ");
String name = input.nextLine(); // ❌ This gets skipped!
```

### সমস্যাটি কী? (What is the Problem?)

##### আপনি যখন `nextInt()`-এর পর `nextLine()` ব্যবহার করেন, তখন **`nextLine()` কাজই করে না** — সেটা স্কিপ হয়ে যায়। মানে প্রোগ্রাম আপনার কাছ থেকে দ্বিতীয় ইনপুট নেওয়ার সুযোগই দেয় না।
---
## 🧪 লাইভ উদাহরণ (Live Example)
```java
System.out.print("Enter your age: ");
int age = input.nextInt();

System.out.print("Enter your name: ");
String name = input.nextLine();

System.out.println("Age: " + age);
System.out.println("Name: " + name);
```

**আপনি যা দেখবেন:**
```text
Enter your age: 25
Enter your name: Age: 25
Name: 
```
👉 **দেখুন সমস্যাটি:**
- "Enter your name:" লেখার পরই সাথে সাথেই আউটপুট চলে এসেছে
- আপনি নাম লেখার কোনো সুযোগই পেলেন না
- `name` ভেরিয়েবলে কিছুই রাখা হয়নি (empty string)

## 🧠 কেন হয়? (Why Does This Happen?)
এর পেছনে আছে **Buffer** নামক একটি জিনিস।

### Solution: 
### `nextLine()` বসানো
```java
System.out.print("Enter age: ");
int age = input.nextInt();

input.nextLine(); // 👈 এই লাইনটি বসান! (এটি \n খেয়ে ফেলবে)

System.out.print("Enter name: ");
String name = input.nextLine(); // ✅ এখন ঠিকমতো কাজ করবে
```

## 📋 দ্রুত মনে রাখার টেবিল (Quick Memory Table)

| আগে যা ব্যবহার করেন | পরে যা ব্যবহার করেন | করণীয়                      |
| ------------------- | ------------------- | --------------------------- |
| `nextInt()`         | `nextLine()`        | মাঝে `input.nextLine()` দিন |
| `nextDouble()`      | `nextLine()`        | মাঝে `input.nextLine()` দিন |
| `next()`            | `nextLine()`        | মাঝে `input.nextLine()` দিন |
| `nextFloat()`       | `nextLine()`        | মাঝে `input.nextLine()` দিন |
| `nextLong()`        | `nextLine()`        | মাঝে `input.nextLine()` দিন |
| `nextLine()`        | `nextLine()`        | ❌ কোনো সমস্যা নেই           |

-----
--------


### 6. Quick Reference Table

|What you want|Code|
|---|---|
|Integer|`int a = input.nextInt();`|
|Double|`double d = input.nextDouble();`|
|Word|`String s = input.next();`|
|Full line|`String line = input.nextLine();`|
|Character|`char c = input.next().charAt(0);`|


---
### 7. Practice Problems

1. Take user's name and age, then print "Hello [name], you are [age] years old"
2. Take two integers from user and print their sum
3. Take a double number from user and print its square

---------
------------
-------------

### 🎯🎯🎯 Topic: Operators in Java

## Operator কী? (What is an Operator?)

Operator হলো **বিশেষ চিহ্ন বা শব্দ** যা ভেরিয়েবল বা ভ্যালুর উপর নির্দিষ্ট অপারেশন করে।
**সহজ ভাষায়:**  
Operator হলো গণিতের মতো — যেমন `+` মানে যোগ, `-` মানে বিয়োগ।
```java
int a = 10;
int b = 5;
int sum = a + b + 3;

// এখানে:
// '+' = Operator
// '=' = Operator
// 'a' আর 'b' = Operands
// '10' আর '5' আর  3 = Constant
// 'a', 'b', 'sum' = Variable
// 'sum = a + b' = Expression
// 'int sum = a + b;' = Statement
// ';' = Statement Terminator
```
## Java Operators-এর প্রকারভেদ : 


| #   | Operator Type | কাজ                |
| --- | ------------- | ------------------ |
| 1   | Arithmetic    | গাণিতিক হিসাব      |
| 2   | Assignment    | মান বসানো          |
| 3   | Relational    | তুলনা করা          |
| 4   | Logical       | শর্ত যাচাই         |
| 5   | Unary         | একক ভেরিয়েবলের কাজ |
| 6   | Ternary       | শর্টকাট if-else    |

<img width="1488" height="718" alt="op" src="https://github.com/user-attachments/assets/a1ce6218-f811-4296-8839-8971468132f0" />


##  1. Arithmetic Operators (গাণিতিক অপারেটর)
**কাজ:** সংখ্যা নিয়ে সাধারণ গণিত করা।

| Operator  চিহ্ন | Operator নাম   | উদাহরণ               | ফলাফল           |     |
| --------------- | -------------- | -------------------- | --------------- | --- |
| +               | Addition       | `sum = 10 + 5`       | `sum = 15`      |     |
| -               | Subtraction    | `diff = 10 - 5`      | `diff = 5`      |     |
| *               | Multiplication | `product = 10 * 5`   | `product = 50`  |     |
| /               | Division       | `quotient = 10 / 5`  | `quotient = 2`  |     |
| %               | Modulus        | `remainder = 10 % 5` | `remainder = 0` |     |

Example:
```java
import java.util.Scanner;

public class ArithmeticOperations {
    public static void main(String[] args) {
        Scanner input = new Scanner(System.in);
        
        // ইউজারের কাছ থেকে দুটি সংখ্যা নেওয়া
        System.out.print("Enter first number: ");
        int a = input.nextInt();
        
        System.out.print("Enter second number: ");
        int b = input.nextInt();
        
        // Arithmetic Operations
        int sum = a + b;        // sum = a + b
        int diff = a - b;       // diff = a - b
        int product = a * b;    // product = a * b
        int quotient = a / b;   // quotient = a / b
        int remainder = a % b;  // remainder = a % b
        
        // Print Methods দিয়ে আউটপুট দেখানো
        System.out.println("\n===== Results =====");
        
        // Method 1: println() - প্রতিটি লাইনে প্রিন্ট করে
        System.out.println("Sum: " + sum);
        System.out.println("Difference: " + diff);
        System.out.println("Product: " + product);
        System.out.println("Quotient: " + quotient);
        System.out.println("Remainder: " + remainder);
        
        // Method 2: print() - একই লাইনে প্রিন্ট করে
        System.out.print("\nUsing print(): ");
        System.out.print("Sum = " + sum + " ");
        System.out.print("Product = " + product);
        
        // Method 3: printf() - ফরম্যাট করে প্রিন্ট করে
        System.out.printf("\n\nUsing printf(): Sum = %d, Product = %d, Remainder = %d\n", sum, product, remainder);
        
        input.close();
    }
}
```
**নমুনা আউটপুট:**
```text
Enter first number: 10
Enter second number: 5

===== Results =====
Sum: 15
Difference: 5
Product: 50
Quotient: 2
Remainder: 0

Using print(): Sum = 15 Product = 50

Using printf(): Sum = 15, Product = 50, Remainder = 0
```



