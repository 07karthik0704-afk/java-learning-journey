# Static Keyword

## Definition

> **`static`**** means the member belongs to the class, not to individual objects.**

---

## 1. Static Variable

```java
class Student {

    static String college = "ABC College";
}
```

### Use

* Shared by all objects.
* Only one copy exists.
* Used for common data.

**Example:** College name, Company name, PI value.

---

## 2. Static Method

```java
class Calculator {

    static void display() {
        System.out.println("Hello");
    }
}

Calculator.display();
```

### Use

* Can be called without creating an object.
* Used for utility/helper methods.

**Example:** `Math.max()`, `Math.sqrt()`

---

## 3. Static Block

```java
class Demo {

    static {
        System.out.println("Static Block");
    }

    public static void main(String[] args) {
        System.out.println("Main Method");
    }
}
```

**Output**

```text
Static Block
Main Method
```

### Use

* Executes once when the class is loaded.
* Used to initialize static variables.

---

# 4 Static Nested Class

## Example

```java
class Outer {

    static int x = 100;

    static class Inner {

        void display() {
            System.out.println("Inside Inner Class");
            System.out.println("x = " + x);
        }
    }

    public static void main(String[] args) {

        // No need to create an Outer object
        Outer.Inner obj = new Outer.Inner();

        obj.display();
    }
}
```

### Output

```text
Inside Inner Class
x = 100
```

---

## Why Static Nested Class?

Normally, an inner class needs an object of the outer class.

```java
class Outer {

    class Inner {

    }
}
```

Usage:

```java
Outer outer = new Outer();
Outer.Inner obj = outer.new Inner();
```

---

But if the inner class is `static`:

```java
class Outer {

    static class Inner {

    }
}
```

Usage:

```java
Outer.Inner obj = new Outer.Inner();
```

No `Outer` object is required.

---

## When is it Used?

* Helper classes.
* Utility classes related only to the outer class.
* Organizing code without creating an outer object.

### Example

```java
class Database {

    static class Connection {

        void connect() {
            System.out.println("Database Connected");
        }
    }

    public static void main(String[] args) {

        Database.Connection db = new Database.Connection();
        db.connect();
    }
}
```

**Output**

```text
Database Connected
```

---

## Memory Trick

```text
Normal Inner Class
------------------
Needs Outer Object

Outer outer = new Outer();
Outer.Inner obj = outer.new Inner();

----------------------------

Static Nested Class
-------------------
No Outer Object Needed

Outer.Inner obj = new Outer.Inner();
```
