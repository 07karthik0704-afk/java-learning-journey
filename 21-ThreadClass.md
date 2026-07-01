```java
class FirstProgram {

    public static void main(String[] args) {

        for(int i=1;i<=4;i++){
             Cake cake=new Cake();
             cake.start();
        }

    }
}

public class Cake extends Thread{

    public void run(){

        System.out.println("Mixing ingredients for cake "+Cake.currentThread().getId());
        System.out.println("Baking cake "+Cake.currentThread().getId());
        System.out.println("Decorating cake "+Cake.currentThread().getId());

    }
}
```

---

# Step 1

```java
Cake cake = new Cake();
```

### What happens?

* `Cake` → Child class of `Thread`.
* `cake` → Reference variable (Stack).
* `new Cake()` → Creates a Cake object (Heap).

Memory:

```text
Stack                    Heap
-----                    -------------------
cake  ------------->     Cake Object
```

---

# Step 2

```java
cake.start();
```

This is the **most important line**.

It **does NOT call `run()` directly**.

Instead:

```text
start()
     │
     ▼
JVM creates a new Thread
     │
     ▼
JVM automatically calls run()
```

So the flow is:

```text
start()
    │
    ▼
New Thread Created
    │
    ▼
run()
```

---

# Step 3

Inside `run()`

```java
System.out.println("Mixing...");
System.out.println("Baking...");
System.out.println("Decorating...");
```

Each thread executes these statements.

---

# Step 4

Loop

```java
for(int i=1;i<=4;i++)
```

Creates

```
Cake 1
Cake 2
Cake 3
Cake 4
```

Each object starts its own thread.

So there are **4 Cake objects** and **4 threads**.

---

# currentThread()

```java
Thread.currentThread().getId();
```

returns the **ID of the currently executing thread**.

Example Output:

```text
Mixing ingredients for cake 11
Mixing ingredients for cake 12
Mixing ingredients for cake 13
Mixing ingredients for cake 14

Baking cake 11
Decorating cake 12
Baking cake 14
Decorating cake 13
...
```

Notice the output may **not** be in order.

---

# Why?

Because the CPU decides:

```text
Thread 11
↓

Thread 14
↓

Thread 12
↓

Thread 13
```

Java doesn't guarantee the execution order.

This is called **Thread Scheduling**.

---

# Why use start() instead of run()?

Suppose you write:

```java
cake.run();
```

Output:

```
Cake 1

↓

Cake 2

↓

Cake 3

↓

Cake 4
```

Everything executes one after another.

No multithreading.

---

If you write:

```java
cake.start();
```

Then:

```
Cake 1
        │
Cake 2  │
        │
Cake 3  │
        │
Cake 4
```

All execute concurrently.

---

# Memory View

```
Main Thread

        │

for Loop

        │

 ┌──────┼──────┬──────┬──────┐
 ▼      ▼      ▼      ▼
Cake1 Cake2 Cake3 Cake4
 │      │      │      │
 ▼      ▼      ▼      ▼
T1     T2     T3     T4
```

---

# Questions

## Why extend Thread?

To create a new thread by overriding the `run()` method.

---

## Why override `run()`?

Because it contains the task that each thread should execute.

---

## Why call `start()`?

`start()` creates a new thread and then invokes `run()` automatically.

---

## Why not call `run()` directly?

Calling `run()` executes it like a normal method in the current thread.

It **does not create a new thread**.

---

# Memory Trick

```text
new Cake()

↓

Creates Object

↓

start()

↓

Creates New Thread

↓

run()

↓

Thread Executes Task
```

---

# Definition

> **To create a thread by extending the `Thread` class, we override the `run()` method and start the thread using `start()`. The `start()` method creates a new thread, and the JVM automatically invokes the `run()` method in that new thread.**

---

