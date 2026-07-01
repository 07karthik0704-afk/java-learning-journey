
## What is Runnable?

> **Runnable is a functional interface that contains only one abstract method: `run()`.**

```java
public interface Runnable {
    void run();
}
```

Instead of extending the `Thread` class, we implement the `Runnable` interface.

---

# Why Runnable?

Java supports **single inheritance**.

If we extend `Thread`, we cannot extend any other class.

```java
class Cake extends Thread {
}
```

❌ Now `Cake` cannot extend another class.

---

Using Runnable:

```java
class Cake implements Runnable {
}
```

Now `Cake` is still free to extend another class if needed.

Example:

```java
class Bakery {
}

class Cake extends Bakery implements Runnable {
}
```

This is why **Runnable is preferred**.

---

# Steps to Create a Thread

### Step 1

Implement Runnable.

```java
class Cake implements Runnable {

    @Override
    public void run() {

    }
}
```

---

### Step 2

Create the Runnable object.

```java
Cake cake = new Cake();
```

---

### Step 3

Pass the Runnable object to the Thread constructor.

```java
Thread thread = new Thread(cake);
```

Here,

- `cake` → Runnable object
- `thread` → Thread object

---

### Step 4

Start the thread.

```java
thread.start();
```

Flow:

```
start()
     │
     ▼
New Thread Created
     │
     ▼
run()
```

---

# Memory Flow

```
Stack                           Heap

cake  -----------------------> Cake Object
thread ----------------------> Thread Object
                                   │
                                   ▼
                             Runnable (cake)
```

The `Thread` object knows which `Runnable` object's `run()` method it should execute.

---

# Why Thread(cake)?

The `Thread` class itself doesn't know what task to perform.

So we pass a `Runnable` object that contains the task (`run()` method).

```
Cake (Runnable)
        │
        ▼
run()

        │
Passed to

Thread(cake)

        │
        ▼
thread.start()

        │
        ▼
run() executes
```

---

# Output

Example:

```
Mixing ingredients for cake 11
Baking cake 11
Decorating cake 11

Mixing ingredients for cake 12
...
```

The execution order is not guaranteed because the CPU schedules the threads.

---

# extends Thread vs implements Runnable

| extends Thread | implements Runnable |
|---------------|---------------------|
| Inherits Thread class | Implements Runnable interface |
| Cannot extend another class | Can extend another class |
| Simpler for small examples | Preferred in real projects |
| Less flexible | More flexible |

---

# Memory Trick

```
Way 1

extends Thread

↓

Override run()

↓

start()

--------------------------

Way 2

implements Runnable

↓

Override run()

↓

Thread(obj)

↓

start()
```

---

# Questions

## Why implement Runnable instead of extending Thread?

Because Java supports single inheritance. Implementing Runnable allows the class to extend another class while still creating a thread.

---

## What does Thread(cake) do?

It creates a Thread object and associates it with the Runnable object (`cake`).

---

## Why call start()?

`start()` creates a new thread, and the JVM automatically calls the `run()` method.

---

## Can we call run() directly?

Yes, but it behaves like a normal method call and **does not create a new thread**.

---

# Definition

> **Runnable is a predefined functional interface used to define a task. A Thread object executes that task by invoking the Runnable object's `run()` method when `start()` is called.**
````

---

```java
Cake cake = new Cake();
Thread thread = new Thread(cake);
```

**Why do we need two objects? Why not just `cake.start()`?**

Because `Cake` is **not a Thread** anymore.

`Cake` only describes **what work to do** (`run()`).

The `Thread` object is responsible for **creating and managing the actual thread**.

Think of it like this:

```text
Runnable (Cake)
----------------
"I know the work."

Thread
-------
"I know how to execute the work concurrently."

Thread + Runnable
-----------------
"I'll execute this work in a new thread."
```

This separation of **task** (`Runnable`) and **thread** (`Thread`) is one of the reasons Java recommends `Runnable` for most applications.

---

