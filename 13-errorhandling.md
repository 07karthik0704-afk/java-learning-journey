#  Exception Handling

## ✅ 1. try

```java
try {
    // Risky code
}
```

Correct.

Purpose:

> Code that may throw an exception.

---

## ✅ 2. catch

```java
catch(Exception e)
```

Correct.

Purpose:

> Handle the exception instead of terminating the program.

---

## ✅ 3. finally

```java
finally{
    System.out.println("No matter what");
}
```

Correct.

Purpose:

> Executes whether an exception occurs or not.

Mostly used for:

* Closing Scanner
* Closing Files
* Closing Database Connections

---

## ✅ 4. Multiple Catch

```java
catch(ClassCastException e){}

catch(Exception e){}
```

Correct.

One important rule:

```java
catch(Exception e){}
catch(ArithmeticException e){}
```

❌ Wrong

Because `Exception` catches everything.

Always write:

```java
catch(ArithmeticException e){}

catch(Exception e){}
```

Specific → General

---

## ✅ 5. throw

```java
throw new ArithmeticException("Age Invalid");
```

Correct.

Purpose:

> Manually throw an exception.

---

## ✅ 6. throws

```java
static void dummyMethod() throws UserDefined
```

Correct.

Purpose:

> Declares that this method may throw an exception.

The caller must handle it.

---

## ✅ 7. User Defined Exception

Correct.

```java
class UserDefined extends Exception
```

Exactly how custom exceptions are created.

---

# One Small Correction

You said:

> Error → programmer cannot handle.
>
> Exception → programmer can handle.

🟡 Almost.

A better explanation:

## Error

Serious JVM/system problems.

Examples:

* OutOfMemoryError
* StackOverflowError

Normally we don't recover from these.

---

## Exception

Problems that an application can anticipate and handle.

Examples:

* Divide by zero
* File not found
* Invalid age
* Invalid input

---

# Exception Hierarchy

```text
Throwable
│
├── Error
│
└── Exception
      │
      ├── Checked Exception
      │
      └── RuntimeException
              │
              └── Unchecked Exception
```

---

# 1. Checked Exception

The **compiler checks** whether you've handled it.

If you don't, your program **won't compile**.

### Example

```java
import java.io.FileReader;

class Demo {
    public static void main(String[] args) {

        FileReader fr = new FileReader("abc.txt");
    }
}
```

Compiler Error:

```text
Unhandled exception type FileNotFoundException
```

Java says:

> "What if `abc.txt` doesn't exist? Handle it first!"

So you must do either:

```java
try {
    FileReader fr = new FileReader("abc.txt");
}
catch(Exception e) {

}
```

or

```java
void demo() throws FileNotFoundException {

}
```

Otherwise, the code **won't compile**.

---

## Why is it called "Checked"?

Because the **compiler checks it before running the program**.

---

# 2. Unchecked Exception

These are **not checked by the compiler**.

Your program compiles successfully.

Example:

```java
class Demo {

    public static void main(String[] args) {

        int a = 10;
        int b = 0;

        System.out.println(a / b);
    }
}
```

Compiler:

```text
✔ No Error
```

Program Runs...

Then:

```text
ArithmeticException: / by zero
```

The compiler didn't stop you.

It happens **only while running**.

That's why it's called **Unchecked**.

---

# Another Example

```java
String name = null;

System.out.println(name.length());
```

Compiles?

✅ Yes

Runs?

❌

Output:

```text
NullPointerException
```

Again...

Compiler didn't force you to handle it.

---

# Simple Comparison

| Checked Exception        | Unchecked Exception              |
| ------------------------ | -------------------------------- |
| Checked by compiler      | Not checked by compiler          |
| Must handle              | Optional to handle               |
| Compile-time checking    | Runtime occurs                   |
| `IOException`            | `ArithmeticException`            |
| `SQLException`           | `NullPointerException`           |
| `ClassNotFoundException` | `ArrayIndexOutOfBoundsException` |

---





