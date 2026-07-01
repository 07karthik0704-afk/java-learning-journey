# What are Predefined Classes?

Definition:

> **Predefined classes are classes already provided by Java. We don't need to create them ourselves; we simply use them.**

Examples:

```java
String
Math
Integer
Double
Character
Scanner
System
Arrays
Object
```

These are all classes written by Java developers and included in the JDK.

---

# Why do we need them?

Imagine Java didn't provide `Math`.

You'd have to write:

```java
class MyMath {

    static int max(int a,int b){
        ...
    }

    static double sqrt(int n){
        ...
    }
}
```

for every project.

Instead, Java already gives you:

```java
Math.max()
Math.sqrt()
Math.pow()
```

---

# The Important Predefined Classes

You do **NOT** need to learn hundreds of methods.

Only the commonly used ones.

---

# 1. String ⭐⭐⭐⭐⭐

You already know Strings.

Important methods:

```java
length()
charAt()
substring()
equals()
equalsIgnoreCase()
contains()
startsWith()
endsWith()
toUpperCase()
toLowerCase()
trim()
replace()
split()
indexOf()
```

These are asked very frequently.

---

# 2. Integer ⭐⭐⭐⭐⭐

### parseInt()

```java
String age = "25";

int a = Integer.parseInt(age);
```

Output

```
25
```

Purpose

> Convert String → int

---

### valueOf()

```java
Integer n = Integer.valueOf("25");
```

Purpose

Returns an Integer object.

(Java also auto-unboxes it when needed.)

---

### toBinaryString()

```java
Integer.toBinaryString(10);
```

Output

```
1010
```

---

### toHexString()

```java
Integer.toHexString(100);
```

---

# 3. Double

```java
Double.parseDouble("12.5");
```

Converts String → double.

---

# 4. Character

Useful methods:

```java
Character.isDigit()
Character.isLetter()
Character.isUpperCase()
Character.isLowerCase()
Character.toUpperCase()
Character.toLowerCase()
```

Example

```java
Character.isDigit('5');
```

Output

```
true
```

---

# 5. Math ⭐⭐⭐⭐⭐

Very important.

```java
Math.max()
Math.min()
Math.sqrt()
Math.pow()
Math.abs()
Math.random()
Math.ceil()
Math.floor()
Math.round()
```

---

# 6. Arrays

```java
Arrays.sort()
Arrays.toString()
Arrays.binarySearch()
Arrays.equals()
```

---

# 7. Object

Most important methods:

```java
toString()

equals()

hashCode()
```

---

# Difference Between parseInt() and valueOf()

This confuses many students.

```java
Integer.parseInt("25");
```

Returns:

```
int
```

---

```java
Integer.valueOf("25");
```

Returns:

```
Integer Object
```

---

# toString()

```java
int n = 25;

String s = Integer.toString(n);
```

Output

```
"25"
```

Converts

```
int → String
```

---

# Memory Trick

```
Predefined Classes
│
├── String
├── Integer
├── Double
├── Character
├── Math
├── Arrays
├── Scanner
└── Object
```

---

