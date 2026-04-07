## Final Keyword in Java

---

## Introduction

- `final` keyword is used to restrict changes  
- It can be applied to variables, methods, and classes  

---

## 1. Final Variable

- Value cannot be changed once assigned  
- Acts like a constant  

### Example:
```java
final int a = 10;
a = 20; // ❌ Error
````

---

## 2. Final Method

* Cannot be overridden in child class

### Example:

```java
class A {
    final void show() {
        System.out.println("Final Method");
    }
}

class B extends A {
    // void show() { } ❌ Error (cannot override)
}
```

---

## 3. Final Class

* Cannot be inherited (no subclass can be created)

### Example:

```java id="fc2k1"
final class A {
}

// class B extends A { } ❌ Error
```

---

## Important Points

* `final` variable → constant value
* `final` method → cannot override
* `final` class → cannot inherit

---

## My Understanding

The `final` keyword is used to restrict modification.
It prevents changing values, overriding methods, and inheriting classes.

---


## Super Keyword in Java

---

## Introduction

- `super` keyword is used to refer to the immediate parent class object  

---

## Uses of super

### 1. Access Parent Class Variable

- Used when parent and child have same variable name  

#### Example:
```java
class A {
    int x = 10;
}

class B extends A {
    int x = 20;

    void show() {
        System.out.println(super.x); // prints 10
    }
}
````

---

### 2. Call Parent Class Method

* Used to call parent class method

#### Example:

```java id="sp2k1"
class A {
    void show() {
        System.out.println("Parent method");
    }
}

class B extends A {
    void show() {
        super.show(); // calls parent method
        System.out.println("Child method");
    }
}
```

---

### 3. Call Parent Class Constructor

* Used to call parent class constructor
* Must be the first statement inside constructor

#### Example:

```java id="sp3k1"
class A {
    A() {
        System.out.println("Parent Constructor");
    }
}

class B extends A {
    B() {
        super(); // calls parent constructor
        System.out.println("Child Constructor");
    }
}
```

---

## Important Points

* Refers to immediate parent class
* Used to resolve naming conflicts
* Helps in calling parent methods and constructors

---

## My Understanding

The `super` keyword is used to access parent class members such as variables, methods, and constructors.

---

## this Keyword in Java

---

## Introduction

- `this` keyword is used to refer to the current object (current instance)

---

## Uses of this

### 1. Access Current Class Variables

- Used when local variable and instance variable have same name  

#### Example:
```java
class Student {

    String name;

    void setName(String name) {
        this.name = name; // refers to current object variable
    }
}
````

---

### 2. Call Current Class Method

* Used to call another method of the same class

#### Example:

```java id="th2k1"
class Demo {

    void show() {
        System.out.println("Show method");
    }

    void display() {
        this.show(); // calling current class method
    }
}
```

---

### 3. Call Current Class Constructor

* Used to call another constructor of the same class
* Must be the first statement

#### Example:

```java id="th3k1"
class Demo {

    Demo() {
        this(10);
        System.out.println("Default Constructor");
    }

    Demo(int x) {
        System.out.println("Parameterized Constructor");
    }
}
```

---

## Important Points

* Refers to current object
* Helps to avoid confusion between variables
* Can call methods and constructors of same class

---

## My Understanding

The `this` keyword is used to refer to the current instance of a class.
It helps in accessing variables, methods, and constructors of the same object.


