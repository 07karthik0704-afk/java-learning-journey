## Interface in Java

---

## Introduction

- An interface is a blueprint of a class  
- It is used to achieve abstraction  
- It contains only method declarations (by default)  

---

## Why We Use Interface

- To achieve 100% abstraction  
- To allow multiple inheritance in Java  
- To define common behavior for different classes  

---

## Key Features

- Declared using `interface` keyword  
- Methods are public and abstract by default  
- Variables are public, static, and final by default  
- Cannot create objects of interface  

---

## Example

```java
interface Animal {
    void sound(); // abstract method
}
````

---

## Implementation

```java id="imp1x"
class Dog implements Animal {

    public void sound() {
        System.out.println("Dog barks");
    }
}
```

---

## Object Creation

```java id="obj1x"
Dog d = new Dog();
d.sound();
```

---

## Multiple Inheritance Using Interface

```java id="multi1x"
interface A {
    void show();
}

interface B {
    void display();
}

class C implements A, B {

    public void show() {
        System.out.println("From A");
    }

    public void display() {
        System.out.println("From B");
    }
}
```

---

## Important Points

* A class can implement multiple interfaces
* Interface supports multiple inheritance
* Helps in loose coupling and better design

---

## My Understanding

Interface is used to achieve abstraction and multiple inheritance.
It defines what a class should do, but not how it does it.


