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


---

# Polymorphism

```text
Polymorphism
│
├── Compile-Time Polymorphism
│      └── Method Overloading
│
└── Runtime Polymorphism
       ├── Method Overriding
       └── Parent Reference = Child Object
           (Used to achieve Runtime Polymorphism)
```

##


---

# Runtime Polymorphism - Parent Reference & Child Object

## Rule

```text
Parent Reference = Child Object   ✅

Child Reference = Parent Object   ❌
```

## Example

```java
class Animal {
    void sound() {
        System.out.println("Animal");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog");
    }
}
```

### Valid

```java
Animal obj = new Dog();
obj.sound();
```

**Output**

```text
Dog
```

**Reason**

* `Dog` **is an** `Animal`.
* The actual object is `Dog`.
* Java executes the overridden method of the actual object at runtime.

---

### Invalid

```java
Dog obj = new Animal();
```

**Reason**

* Every `Dog` is an `Animal`.
* But every `Animal` is **not** a `Dog`.
* An `Animal` could be a `Dog`, `Cat`, or `Lion`.
* Therefore, Java does not allow assigning a parent object to a child reference.

---

## Easy Example

```text
Vehicle
   ▲
   │
 Car
```

✅ Valid

```java
Vehicle v = new Car();
```

❌ Invalid

```java
Car c = new Vehicle();
```

Because every **Car is a Vehicle**, but every **Vehicle is not a Car**.

---

## Memory Trick

```text
General
   ▲
Parent

Specific
   ▲
Child
```

> **A child object can always be treated as its parent, but a parent object cannot automatically be treated as its child.**
----

# Why Runtime Polymorphism?

## Without Runtime Polymorphism

```java
Dog dog = new Dog();
Cat cat = new Cat();
Lion lion = new Lion();

dog.sound();
cat.sound();
lion.sound();
```

### Problem

* Need separate reference variables.
* Code increases as new child classes are added.
* Less reusable.

---

## With Runtime Polymorphism

```java
Animal obj;

obj = new Dog();
obj.sound();

obj = new Cat();
obj.sound();

obj = new Lion();
obj.sound();
```

### Output

```text
Bow Bow...
Meow...
Roar...
```

### Benefits

* One parent reference.
* Different child objects.
* Same method call (`sound()`).
* Different behavior at runtime.

---

## Adding a New Child

```java
class Elephant extends Animal {

    @Override
    void sound() {
        System.out.println("Trumpet...");
    }
}
```

No need to change the existing design.

Simply write:

```java
obj = new Elephant();
obj.sound();
```

Output

```text
Trumpet...
```

---

## Why Use Runtime Polymorphism?

* ✔ One parent reference can refer to many child objects.
* ✔ Same method call, different behavior.
* ✔ Flexible code.
* ✔ Reusable code.
* ✔ Easy to maintain and extend.

---

##



