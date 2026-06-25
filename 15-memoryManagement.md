# Java Fundamentals - JVM Memory (Basics)

## 1. Method Area

### What does it store?

* Class Blueprint
* Class Name
* Method Definitions
* Static Variables
* Constructors
* Class Metadata

**Example**

```java
class Employee {
    String name;
    int age;
    static String company = "ABC";
    void work() {}
}
```

Before creating any object, the **Method Area** already knows:

```text
Employee
name
age
company = "ABC"
work()
```

> **Method Area stores the blueprint, not object values.**

---

## 2. Heap Memory

### What does it store?

* Objects
* Instance Variables
* Instance Variable Values

**Example**

```java
Employee e1 = new Employee();
e1.name = "Tony";
e1.age = 22;
```

Heap:

```text
Employee Object
---------------
name = "Tony"
age  = 22
```

> **Heap stores the actual object and its data.**

---

## 3. Stack Memory

### What does it store?

* Local Variables
* Method Parameters
* Reference Variables
* Stack Frames

**Example**

```java
Employee e1 = new Employee();
int a = 10;
```

Stack:

```text
main()

a = 10

e1 ───────▶ 0x101
```

Heap:

```text
0x101

Employee Object
---------------
name = null
age  = 0
```

> **The Stack stores the reference. The Heap stores the actual object.**

---

# Memory Summary

| Memory          | Stores                                                                |
| --------------- | --------------------------------------------------------------------- |
| **Method Area** | Class Blueprint, Methods, Static Variables, Metadata                  |
| **Heap**        | Objects, Instance Variables, Instance Variable Values                 |
| **Stack**       | Local Variables, Method Parameters, Reference Variables, Stack Frames |

---

# Memory Trick

```text
Method Area
    │
    └── Blueprint

Stack
    │
    └── Reference (Address)

Heap
    │
    └── Actual Object + Data
```

## Easy Rule

* **Class is loaded** → Method Area
* **`new` keyword** → Heap
* **Inside a method** → Stack
