# Scanner (Java)

## What is Scanner?

> **Scanner is a predefined class used to read input from the user through the keyboard.**

```java
import java.util.Scanner;
```

---

# Creating a Scanner Object

```java
Scanner sc = new Scanner(System.in);
```

### Explanation

* `Scanner` → Predefined Class.
* `sc` → Reference Variable (Stored in Stack).
* `new` → Creates a Scanner object in the Heap.
* `System.in` → Standard input stream (Keyboard input).
* `Scanner` reads data from `System.in`.

### Flow

```text
Keyboard
    │
    ▼
System.in
    │
    ▼
Scanner Object
    │
    ▼
Program Variable
```

---

# Common Methods

| Method             | Description          |
| ------------------ | -------------------- |
| `nextInt()`        | Reads an Integer     |
| `nextDouble()`     | Reads a Double       |
| `nextFloat()`      | Reads a Float        |
| `nextLong()`       | Reads a Long         |
| `nextBoolean()`    | Reads a Boolean      |
| `next()`           | Reads a Single Word  |
| `nextLine()`       | Reads an Entire Line |
| `next().charAt(0)` | Reads a Character    |

---

# next() vs nextLine()

### next()

* Reads only one word.
* Stops reading at a space.

**Input**

```text
Tony Stark
```

```java
sc.next();
```

**Output**

```text
Tony
```

---

### nextLine()

* Reads the complete line.
* Includes spaces.

**Input**

```text
Tony Stark
```

```java
sc.nextLine();
```

**Output**

```text
Tony Stark
```

---

# Why does nextLine() skip input?

Example

```java
Scanner sc = new Scanner(System.in);

int age = sc.nextInt();
String name = sc.nextLine();
```

**Input**

```text
21
Tony
```

**Output**

```text
Age = 21
Name =
```

### Reason

`nextInt()` reads only the integer.

The **Enter key (`\n`) remains in the input buffer.**

When `nextLine()` executes next, it reads that leftover newline instead of waiting for new input.

### Solution

```java
int age = sc.nextInt();
sc.nextLine();        // Consume leftover '\n'
String name = sc.nextLine();
```

---

# Why use close()?

```java
sc.close();
```

### Purpose

* Releases the Scanner resources.
* Prevents resource leaks.
* Considered good programming practice.

### Real-Life Example

```text
Borrow a Library Book
        ↓
Read It
        ↓
Return It ✅
```

Similarly,

```text
Create Scanner
        ↓
Use Scanner
        ↓
Close Scanner ✅
```

---

# Memory View

```text
Stack
------
sc  ----------------------┐
                           │
                           ▼
Heap                  Scanner Object
                           │
                           ▼
                     System.in
                           │
                           ▼
                       Keyboard
```

---

# Interview Questions

### Why do we use Scanner?

To read input from the user through the keyboard.

---

### What is System.in?

It is the standard input stream that receives input from the keyboard.

---

### What is `sc`?

A reference variable that points to the Scanner object.

---

### Where is the Scanner object stored?

In the Heap memory.

---

### What does `new` do?

Creates a Scanner object in the Heap memory.

---

### Why use `close()`?

To release resources and avoid resource leaks.

---

# Complete Example

```java
import java.util.Scanner;

class Demo {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter Name: ");
        String name = sc.nextLine();

        System.out.print("Enter Age: ");
        int age = sc.nextInt();

        System.out.println("Name : " + name);
        System.out.println("Age  : " + age);

        sc.close();
    }
}
```

---

# Memory Trick

```text
Scanner
│
├── Import
├── Create Object
├── Read Input
├── Process Data
└── Close Scanner
```

## One-Line Interview Definition

> **Scanner is a predefined Java class used to read user input from the keyboard through `System.in`. It creates a Scanner object that reads different types of data such as integers, strings, doubles, and characters.**
