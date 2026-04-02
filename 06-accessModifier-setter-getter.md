## Access Modifiers in Java

- Access modifiers are used to control the visibility of classes, variables, and methods

---

## Types of Access Modifiers

### 1. public
- Accessible from anywhere  
- Available to all classes and all packages  

---

### 2. private
- Accessible only within the same class  
- Cannot be accessed outside the class  

---

### 3. protected
- Accessible within the same package  
- Also accessible in subclasses (even in different packages)  

---

### 4. default (no modifier)
- Accessible only within the same package  
- Not accessible outside the package  

---

## Summary Table

| Modifier   | Same Class | Same Package | Subclass (other package) | Other Packages |
|-----------|-----------|--------------|--------------------------|----------------|
| public    | ✅        | ✅           | ✅                       | ✅             |
| private   | ✅        | ❌           | ❌                       | ❌             |
| protected | ✅        | ✅           | ✅                       | ❌             |
| default   | ✅        | ✅           | ❌                       | ❌             |

---

## My Understanding
Access modifiers control how and where variables, methods, and classes can be accessed.  
They help in securing data and controlling visibility in a program.


---


## Getter and Setter Methods

- Getter and Setter methods are used to access and update private variables
- They help in implementing **Encapsulation**

---

## Why We Use Getter and Setter

- To protect data from direct access  
- To control how variables are accessed and modified  
- To provide security and validation  

---

## Example

```java
public class Student {

    private String name;

    // Getter method
    public String getName() {
        return name;
    }

    // Setter method
    public void setName(String name) {
        this.name = name;
    }
}
````

---

## Usage

```java
Student s = new Student();

s.setName("Karthik");   // setting value
System.out.println(s.getName()); // getting value

```
---

## Important Concept: Encapsulation

* Wrapping data (variables) and methods together in a class
* Restricting direct access using `private`
* Accessing data using public methods (getters/setters)

---

## My Understanding

Getter and Setter methods provide controlled access to variables.
Instead of accessing variables directly, we use methods to improve security and maintain control over data.

