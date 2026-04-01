# Day 1 - Basics

## 1 - Two Types of Programming

### 1. Procedural Programming
- In this approach, the program is written using methods (functions).
- Execution happens step by step.
- Focus is on procedures or functions.

### 2. Object-Oriented Programming (OOP)
- In this approach, the program is structured using classes and objects.
- A class contains methods and statements.
- Flow: Class → Methods → Statements (lines of code)
- Focus is on organizing code using objects.

## My Understanding
Procedural programming is based on functions and step-by-step execution, while OOP organizes code using classes and methods, making it more structured and reusable.

## 2 - Printing in Java
- Used to display output on the console

### Example:
```java
System.out.println("Hello World");
```
- System → predefined class
- out → output stream
- println() → method to print with a new line

### Compile:
```java
javac Sample.java
java Sample
```

## What Happens Internally

### Compilation Phase
- The Java compiler (`javac`) checks for errors  
- Converts `.java` file into `.class` file  
- The `.class` file contains bytecode  

### Execution Phase
- JVM (Java Virtual Machine) runs the `.class` file  
- Converts bytecode into machine code  
- Executes the program and shows output  

---

## My Understanding

Java follows a two-step process: compilation and execution.  
First, the code is converted into bytecode, then JVM executes it, making Java platform independent.

---

## 3 - Semicolon in Java (`;`)

- The semicolon (`;`) is used to mark the end of a statement in Java
- It tells the compiler that the line of code is complete


## Variables and Data Types in Java

### Variables

* Variables are used to store values
* They help us reuse data later in the program

### Example:

```java
int a = 10;
```

---

## Data Types

* Data types define what kind of data a variable can store

### Primitive Data Types

| Data Type | Size (in bits) | Example           |
| --------- | -------------- | ----------------- |
| byte      | 8 bits         | byte a = 10;      |
| short     | 16 bits        | short a = 100;    |
| int       | 32 bits        | int a = 1000;     |
| long      | 64 bits        | long a = 1000L;   |
| float     | 32 bits        | float a = 10.5f;  |
| double    | 64 bits        | double a = 10.5;  |
| boolean   | 1 bit*         | boolean a = true; |
| char      | 16 bits        | char c = 'A';     |

> *Boolean size is not officially defined (depends on JVM), but it logically stores `true` or `false`.*

---

## Types of Data Types

### 1. Primitive Data Types

* Store actual values
* Memory is allocated automatically

#### Example:

```java
int a = 10;
int b = a;

a = 30;
```

#### Explanation:

* `b` will NOT change
* Because primitive types store separate copies of values

---

### 2. Reference Data Types

* Store the address (reference) of an object
* Memory is created using the `new` keyword

#### Example:

```java
Point a = new Point(5, 4);
Point b = a;

a.x = 7;
```

#### Explanation:

* Both `a` and `b` refer to the same object
* So changing `a.x` will also affect `b.x`

---

## My Understanding

Variables store data, and data types define what kind of data is stored.

Primitive types store actual values independently, while reference types share memory, so changes affect all references.

---
## Keywords vs Reserved Words in Java

* Both **keywords** and **reserved words** **cannot be used as identifiers** ✔️

---

### 🔑 Keywords

* Used in Java programs
* Have special meaning
* Examples:
  `class`, `int`, `void`, `if`

---

### 🚫 Reserved Words

* Reserved by Java (cannot be used as identifiers)
* Includes:

  * All **keywords**
  * Some **unused words**

#### Examples of unused reserved words:

* `goto`
* `const`

---

## 🧠 Final Conclusion

* **All keywords are reserved and used in Java**
* **Some reserved words are NOT used in Java programs**

---

## 💥 Simple Table

| Type           | Used in Program | Can use as identifier |
| -------------- | --------------- | --------------------- |
| Keywords       | Yes             | No                    |
| Reserved Words | Some No         | No                    |

---

## ⚡ One-line Memory Trick

* Keyword = used
* Reserved = blocked

---

## Variables and Identifiers

### Variable
- A variable is used to store values
- It allows us to use the data later in the program

---

### Identifier
- An identifier is the name given by the programmer
- It is used to identify different elements in a program

#### Examples of identifiers:
- Variable name → `a`
- Method name → `main()`
- Class name → `Sample`

---

## My Understanding
Variables are used to store data, and identifiers are the names we give (like variable name, method name, class name) so that we can use them later in the program.
