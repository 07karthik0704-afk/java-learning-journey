## Types of Inheritance in Java

---

### 1. Single Inheritance
- One parent class → one child class

#### Example:
```java
class A {
    void show() {
        System.out.println("Class A");
    }
}

class B extends A {
    void display() {
        System.out.println("Class B");
    }
}
````

---

### 2. Multilevel Inheritance

* A chain of inheritance (A → B → C)

#### Example:

```java id="mlv1"
class A {
    void show() {
        System.out.println("Class A");
    }
}

class B extends A {
}

class C extends B {
}
```

---

### 3. Hierarchical Inheritance

* One parent class → multiple child classes

#### Example:

```java id="hr1"
class A {
    void show() {
        System.out.println("Class A");
    }
}

class B extends A {
}

class C extends A {
}
```

---

### 4. Multiple Inheritance (Not Supported with Classes)

* One child class inheriting from multiple parent classes

❌ Not supported in Java using classes (to avoid ambiguity)

#### Wrong Example:

```java id="mul1"
class A { }
class B { }

class C extends A, B { } // ❌ Not allowed
```

---

### 5. Hybrid Inheritance

* Combination of multiple types of inheritance

❌ Not supported directly using classes in Java
✅ Can be achieved using interfaces

---

## Important Notes

* Java supports:

  * Single
  * Multilevel
  * Hierarchical

* Java does NOT support:

  * Multiple inheritance (with classes)
  * Hybrid inheritance (directly with classes)

---

## My Understanding

Inheritance allows classes to reuse code.
Java supports single, multilevel, and hierarchical inheritance, but avoids multiple inheritance with classes to prevent confusion.




