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
**Why?**  
`nextInt()` leaves a newline character `\n` in buffer. `nextLine()` reads that `\n` immediately.

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



