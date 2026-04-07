## Abstract Class and Abstract Method in Java

---

## Introduction

- Abstract class is used to achieve abstraction  
- It helps in hiding implementation details and showing only essential features  

---

## Why We Use Abstract Class

- To achieve abstraction  
- To define a common structure for multiple classes  
- To force child classes to implement required methods  

---

## Abstract Class

- Declared using `abstract` keyword  
- Cannot create objects directly  
- Can have:
  - Abstract methods (no body)  
  - Normal methods (with body)  

---

### Example:
```java
abstract class Animal {

    abstract void sound(); // abstract method

    void eat() {
        System.out.println("Animal is eating");
    }
}
````

---

## Abstract Method

* A method without implementation (no body)
* Only declaration is provided
* Must be implemented in child class

---

### Example:

```java id="am2x1"
abstract void sound();
```

---

## Implementation (Subclass)

```java id="impl3k"
class Dog extends Animal {

    void sound() {
        System.out.println("Dog barks");
    }
}
```

---

## Object Creation

```java id="obj4k"
Dog d = new Dog();   // ✅ allowed
// Animal a = new Animal(); ❌ not allowed
```

---

## Difference: Normal Class vs Abstract Class

| Feature         | Normal Class | Abstract Class      |
| --------------- | ------------ | ------------------- |
| Object Creation | ✅ Yes        | ❌ No                |
| Methods         | Only normal  | Normal + Abstract   |
| Use             | General      | Partial abstraction |

---

## Important Points

* Abstract class cannot be instantiated
* Child class must implement abstract methods
* Can use constructors and variables

---


