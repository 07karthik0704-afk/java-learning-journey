## Methods in Java

- Methods are used to perform a specific task
- They help in reusing code when needed

---

## Important Note

- In Java, everything must be written inside a class
- There are no standalone functions like in some other languages
- All functions in Java are called **methods**

---

## Method Definition and Calling

### Method Definition
- Writing the method (what it does)

### Example:
```java
void greet() {
    System.out.println("Hello");
}
````

---

### Method Calling

* Using (invoking) the method

```java
greet();
```

---

## Types of Methods

### 1. Void Method

* Does not return any value

#### Example:

```java
void display() {
    System.out.println("Hello");
}
```

---

### 2. Non-Void Method

* Returns a value

#### Example:

```java
int add(int a, int b) {
    return a + b;
}
```

---

## Parameters and Arguments

### Parameters

* Variables defined in method definition

```java
int add(int a, int b)
```

👉 `a`, `b` are parameters

---

### Arguments

* Actual values passed during method call

```java
add(5, 3);
```

👉 `5`, `3` are arguments

---

## Recursion in Java

- Recursion is a technique where a method calls itself

---

## Why We Use Recursion

- To solve problems by breaking them into smaller subproblems  
- Makes code simpler and more readable in some cases  
- Commonly used in:
  - Factorial
  - Fibonacci
  - Tree structures

---

## Key Concepts

### 1. Base Case
- The condition where recursion stops  
- Prevents infinite execution  

### 2. Recursive Case
- The part where the method calls itself  

---

## Example: Printing Natural Numbers

```java
public class Main {
    public static void main(String[] args) {
        natnum(10);
    }

    public static void natnum(int n) {
        if (n == 1) {
            System.out.print("1");
        } else {
            System.out.print(n + " ");
            natnum(n - 1);
        }
    }
}
````

---

## Explanation

* Starts with `natnum(10)`
* Prints `10` and calls `natnum(9)`
* Continues until `n == 1`
* Stops at base case

---

## Flow

natnum(10) → natnum(9) → natnum(8) → ... → natnum(1)

---

## Important Note

* If there is no base case, recursion will run infinitely
* This leads to **StackOverflowError**

---

## My Understanding

Recursion is when a method calls itself to solve smaller parts of a problem.
It must always include a base case to stop execution and avoid infinite recursion.



