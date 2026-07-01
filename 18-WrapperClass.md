# Wrapper Class

## What is a Wrapper Class?

> **A Wrapper Class is a predefined Java class that wraps (converts) a primitive data type into an object.**

Example:

```text
Primitive        Wrapper Class
---------        -------------
byte      --->   Byte
short     --->   Short
int       --->   Integer
long      --->   Long
float     --->   Float
double    --->   Double
char      --->   Character
boolean   --->   Boolean
```

---

# Why do we need Wrapper Classes?

Suppose we have:

```java
int age = 25;
```

Question:

Can we do this?

```java
age.toBinaryString();
```

❌ No.

Why?

Because:

```text
int
```

is **not an object**.

It is just a primitive value.

---

Now look at this:

```java
Integer age = 25;
```

Now we can use:

```java
Integer.toBinaryString(age);

Integer.max(10,20);

Integer.parseInt("25");
```

Because **Integer is a class**.

Classes can have methods.

---

# Primitive vs Wrapper

| Primitive         | Wrapper                |
| ----------------- | ---------------------- |
| int               | Integer                |
| Only stores value | Stores value + methods |
| Faster            | Slightly slower        |
| Not an object     | Object                 |

---

# Example

```java
int a = 10;

System.out.println(a);
```

Output

```
10
```

Nothing special.

---

Wrapper:

```java
Integer a = 10;

System.out.println(Integer.toBinaryString(a));
```

Output

```
1010
```

---

# Why Java Created Wrapper Classes?

Imagine Java only had primitives.

```java
int
double
char
```

There would be no methods like:

```java
parseInt()

valueOf()

toBinaryString()

compare()
```

Java solved this by creating wrapper classes.

---

# Boxing

Old Java (Before Java 5)

```java
Integer obj = new Integer(10);
```

Primitive

↓

Object

This process is called:

> **Boxing**

---

# Unboxing

```java
Integer obj = new Integer(10);

int a = obj.intValue();
```

Object

↓

Primitive

This is called:

> **Unboxing**

---

# Autoboxing (Java 5+)

Java automatically performs boxing.

Instead of writing:

```java
Integer obj = new Integer(10);
```

We simply write:

```java
Integer obj = 10;
```

Java automatically converts

```text
10
```

↓

```text
Integer Object
```

This is called:

> **Autoboxing**

---

# Auto Unboxing

Instead of:

```java
int a = obj.intValue();
```

We simply write:

```java
Integer obj = 10;

int a = obj;
```

Java automatically converts

```text
Integer
```

↓

```text
int
```

This is called:

> **Auto Unboxing**

---

# Visualization

## Primitive

```text
Stack

a = 10
```

---

## Wrapper

```text
Stack                 Heap

obj  ------------->   Integer Object
                           |
                           10
```

Wrapper class creates an object.

Primitive does not.

---

# Common Wrapper Methods

## Integer

```java
Integer.parseInt("25");
```

String → int

---

```java
Integer.valueOf("25");
```

String → Integer Object

---

```java
Integer.toBinaryString(10);
```

Decimal → Binary

---

```java
Integer.toHexString(100);
```

Decimal → Hexadecimal

---

```java
Integer.max(10,20);
```

Maximum value

---

## Character

```java
Character.isDigit('5');

Character.isLetter('A');

Character.isUpperCase('A');

Character.isLowerCase('a');
```

---

## Double

```java
Double.parseDouble("12.5");
```

---

## Why do we need Wrapper Classes?

**Answer:**

> Primitive data types are not objects and cannot have methods. Wrapper classes convert primitive values into objects and provide many useful predefined methods. They are also required in places where Java APIs work only with objects.

---

# Memory Trick

```text
Primitive
---------
Stores only value

↓

Wrapper Class
-------------
Stores value

+

Provides useful methods

+

Behaves like an Object
```

---

# Summary

```text
Primitive
---------
int
double
char
boolean

↓

Wrapper Class
-------------
Integer
Double
Character
Boolean

↓

Benefits
--------
✔ Object
✔ Useful Methods
✔ Autoboxing
✔ Unboxing
```

---


```java
ArrayList<int> list = new ArrayList<>();   // ❌
```

But this is:

```java
ArrayList<Integer> list = new ArrayList<>();   // ✅
```

