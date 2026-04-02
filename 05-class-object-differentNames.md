## Classes and Objects in Java

---

## Difference Between Procedural and OOP

### Procedural Programming
- Focus is on functions (methods)
- Execution is step by step
- Data and functions are separate

### Object-Oriented Programming (OOP)
- Focus is on objects and classes
- Combines data and methods together
- Makes code reusable and organized

---

## Class and Object (Real-Life Example)

- A **class** is like a blueprint or template  
- An **object** is an instance of that class  

### Example:
- College creates an **original form** → this is the **class**
- Xerox copies given to students → these are **objects**
- Each student filling their own details → **instance (object with data)**

---

## Class Definition

```java
public class AppForm {

    String name;
    int age;

    void display() {
        System.out.println("name = " + name);
        System.out.println("Age = " + age);
    }
}
````

---

## Members of a Class

* **Variables (Data Members)**:

  * `name`
  * `age`

* **Methods (Member Functions)**:

  * `display()`

---

## Object Creation

```java
AppForm student1 = new AppForm();
```

* `AppForm` → class
* `student1` → object
* `new` → creates object in memory

---

## Accessing Members

```java
student1.name = "Karthik";
student1.age = 20;

student1.display();
```

---

## My Understanding

A class is a blueprint, and objects are instances created from it.
Each object can store different data but shares the same structure and behavior defined in the class.

---

## 🧠 Easy memory
👉 Class = blueprint  
👉 Object = real thing  
👉 Instance = object with data  

---


