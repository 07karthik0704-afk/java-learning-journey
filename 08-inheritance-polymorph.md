## Inheritance in Java

- Inheritance is a mechanism where one class acquires the properties and methods of another class

---

## Why We Use Inheritance

- To reuse existing code  
- To avoid code duplication  
- To improve code organization  

---

## Parent and Child Class

- **Parent Class (Super Class)** → class whose properties are inherited  
- **Child Class (Sub Class)** → class that inherits from parent  

---

## Using `extends` Keyword

- In Java, inheritance is achieved using the `extends` keyword  

### Example:
```java
class Animal {

    void eat() {
        System.out.println("Animal is eating");
    }
}

class Dog extends Animal {

    void bark() {
        System.out.println("Dog is barking");
    }
}
````

---

## Usage

```java id="n8f4xp"
Dog d = new Dog();

d.eat();   // inherited from Animal
d.bark();  // own method
```

---

## Important Points

* Child class can access parent class methods and variables
* Promotes code reuse
* Java supports single inheritance using classes

---

## My Understanding

Inheritance allows one class to reuse the properties and methods of another class using the `extends` keyword, making code more reusable and organized.

---

## Polymorphism in Java

- Polymorphism means "many forms"
- It allows the same method name to behave differently in different situations

---

## Types of Polymorphism

### 1. Compile-Time Polymorphism (Method Overloading)
- Same method name with different parameters (signature)
- Decided at compile time

#### Example:
```java
class MathOps {

    int add(int a, int b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
}
````

---

### 2. Runtime Polymorphism (Method Overriding)

* Method in child class overrides parent class method
* Decided at runtime

#### Example:

```java id="rt5k2p"
class Animal {
    void sound() {
        System.out.println("Animal sound");
    }
}

class Dog extends Animal {
    void sound() {
        System.out.println("Dog barks");
    }
}
```

---

## Important Points

* Same method name can be used with different behaviors
* Method overloading → different parameters
* Method overriding → same method in parent and child class

---

## My Understanding

Polymorphism means one method can have many forms.
It allows the same method name to perform different tasks based on parameters or implementation.

---

## Names of parent and child

| Concept      | Names                       |
| ------------ | --------------------------- |
| Parent Class | Parent / Base / Super Class |
| Child Class  | Child / Derived / Sub Class |


