## Static Keyword in Java

---

## Introduction

- `static` keyword is used for memory management  
- It belongs to the class rather than the object  

---

## Static Method

### Key Points

- Can be called using class name (no object needed)  
- Saves memory (no need to create object)  
- Can access only static data directly  

---

### Example:
```java
class Demo {

    static void show() {
        System.out.println("Static Method");
    }

    public static void main(String[] args) {
        Demo.show(); // called using class name
    }
}
````

---

## Why main() is static

```java
public static void main(String[] args)
```

* JVM calls `main()` without creating object
* So it must be `static` to be accessed directly using class name

---

## Static Variable (Static Field)

* Shared among all objects
* Only one copy is created in memory

---

### Example:

```java id="st2k1"
class Demo {

    static int count = 0;

    Demo() {
        count++;
        System.out.println(count);
    }
}
```

---

### Explanation

* All objects share the same `count` variable
* Change in one object affects all

---

## Important Points

* Static members belong to class, not objects
* Access using: `ClassName.member`
* Static variables are shared across objects

---

## My Understanding

The `static` keyword is used to create class-level variables and methods.
It allows access without object creation and helps in saving memory by sharing data among all objects.

---
