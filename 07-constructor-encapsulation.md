## Constructors in Java

- A constructor is a special method used to initialize objects

---

## Key Points

- Constructor name must be the same as the class name  
- It is called automatically when an object is created  
- It does not have any return type (not even `void`)  
- It is usually used to initialize values
- Called **once per object creation**

---

## Why We Use Constructor

- To initialize object values at the time of creation  
- To avoid setting values manually again and again  
- Helps in writing cleaner and more organized code  

---

## Types of Constructors

### 1. Default Constructor
- Constructor with no parameters  
- If we don’t create any constructor, Java provides a default one  

#### Example:
```java
class Student {
    Student() {
        System.out.println("Default Constructor Called");
    }
}
````

---

### 2. Parameterized Constructor

* Constructor with parameters
* Used to initialize values while creating object

#### Example:

```java id="g7h3ks"
class Student {
    String name;

    Student(String name) {
        this.name = name;
    }
}
```

---

## Object Creation

```java id="j9f4lm"
Student s1 = new Student("Karthik");
```

* Constructor is called automatically here

---

## Important Difference

* Constructor → used for initialization
* Method → used for performing actions

---

## My Understanding

Constructors are special methods used to initialize objects.
They are called automatically when an object is created and help in setting initial values easily.

---

## Encapsulation in Java

- Encapsulation is the process of binding data (variables) and methods together into a single unit (class)

---

## How Encapsulation is Achieved

- By declaring variables as `private`
- By providing public methods (getter and setter) to access and modify data

---

## Example

```java
class Student {

    private String name;

    // Setter method
    public void setName(String name) {
        this.name = name;
    }

    // Getter method
    public String getName() {
        return name;
    }
}
````

---

## Usage

```java id="f8k2pl"
Student s = new Student();

s.setName("Karthik");
System.out.println(s.getName());
```

---

## Advantages of Encapsulation

* Provides data security
* Controls access to variables
* Makes code more flexible and maintainable
* Allows validation before setting values

---

## My Understanding

Encapsulation means binding data and methods together in a class and controlling access using getter and setter methods.

---

- Encapsulation = **concept**
- Getter/Setter = **tool to achieve it**

---

## ⚡ Easy memory
👉 Encapsulation = data hiding + controlled access  

---

