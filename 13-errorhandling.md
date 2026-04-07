## Exception Handling in Java

---

## Difference Between Error and Exception

### Error
- Serious problem that cannot be handled by the program  
- Occurs due to system issues  
- Example: OutOfMemoryError  

---

### Exception
- Problems that occur during program execution  
- Can be handled using code  
- Example: ArithmeticException (divide by zero)  

---

## Example: Divide by Zero

```java
int a = 10;
int b = 0;

int result = a / b; // ❌ Runtime Exception
````

* This will cause an **ArithmeticException**

---

## Handling Exception using try-catch

```java
try {
    int a = 10;
    int b = 0;
    int result = a / b;
} catch (ArithmeticException e) {
    System.out.println("Cannot divide by zero");
}
```

---

## Explanation

* `try` → contains risky code
* `catch` → handles the exception
* If exception occurs, program will not crash

---

## Important Points

* Exceptions occur at runtime
* try-catch prevents program from crashing
* Each exception type can be handled separately

---

## My Understanding

Exception handling is used to handle runtime errors and prevent program crashes.
Using try-catch, we can safely manage errors like division by zero.


- > error vs exception  

👉 ✔️ Good  
👉 Just remember:
- Error → cannot handle  
- Exception → can handle  

---


