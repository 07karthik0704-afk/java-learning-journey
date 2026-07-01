# synchronized + join Example

## Program

### CakeCounter.java

```java
package sync;

public class CakeCounter {

    int counter = 0;

    synchronized void increment() {
        counter++;
    }
}
```

---

### Team.java

```java
package sync;

public class Team extends Thread {

    CakeCounter cake;

    Team(CakeCounter cake) {
        this.cake = cake;
    }

    @Override
    public void run() {

        for (int i = 1; i <= 10; i++) {
            cake.increment();
        }

    }
}
```

---

### Bakery.java

```java
package sync;

public class Bakery {

    public static void main(String[] args) {

        CakeCounter cake = new CakeCounter();

        Team teamA = new Team(cake);
        Team teamB = new Team(cake);

        teamA.start();
        teamB.start();

        try {
            teamA.join();
            teamB.join();
        } catch (InterruptedException e) {
            e.printStackTrace();
        }

        System.out.println(cake.counter);

    }
}
```

---

# Step-by-Step Explanation

## Step 1

```java
CakeCounter cake = new CakeCounter();
```

Creates **one CakeCounter object**.

Initial value:

```
counter = 0
```

---

## Step 2

```java
Team teamA = new Team(cake);
Team teamB = new Team(cake);
```

Both Team objects receive the **same CakeCounter object**.

Memory

```
Team A
   │
   ▼
CakeCounter
counter = 0
   ▲
   │
Team B
```

Both threads share the same object.

---

## Step 3

```java
teamA.start();
teamB.start();
```

Creates two threads.

```
Main Thread
      │
 ┌────┴────┐
 ▼         ▼
Team A   Team B
```

Both threads start executing the `run()` method.

---

## Step 4

```java
for(int i=1;i<=10;i++){
    cake.increment();
}
```

Each thread increments the counter 10 times.

Expected:

```
Team A = 10

Team B = 10

Total = 20
```

---

# Why synchronized?

```java
synchronized void increment(){

    counter++;

}
```

Only **one thread** can execute `increment()` at a time.

Example

```
Thread A

LOCK 🔒

counter++

Unlock 🔓

------------------

Thread B

LOCK 🔒

counter++

Unlock 🔓
```

This prevents both threads from modifying `counter` simultaneously.

---

# What happens without synchronized?

Suppose

```
counter = 5
```

Thread A reads

```
5
```

Before updating...

Thread B also reads

```
5
```

Now

Thread A writes

```
6
```

Thread B also writes

```
6
```

Expected

```
7
```

Actual

```
6
```

One increment is lost.

This is called a **Race Condition**.

---

# Why join()?

```java
teamA.join();
teamB.join();
```

The Main Thread waits until both worker threads finish.

Without `join()`

```
Main Thread

↓

Start Team A

↓

Start Team B

↓

Print Counter
```

Possible Output

```
5

or

12

or

17
```

because the threads may still be running.

---

With `join()`

```
Main Thread

↓

Start Team A

↓

Start Team B

↓

WAIT

↓

Team A Finished

↓

Team B Finished

↓

Print Counter
```

Output

```
20
```

Always correct.

---

# Memory Flow

```
                 Main Thread
                      │
         ┌────────────┴────────────┐
         ▼                         ▼
    Team A Thread             Team B Thread
         │                         │
         └────────────┬────────────┘
                      ▼
              CakeCounter Object
                 counter = 0
                      │
         synchronized increment()
                      │
                 LOCK 🔒
                      │
                 counter++
                      │
                UNLOCK 🔓
```

---

# Key Points

### synchronized

- Protects shared data.
- Allows only one thread at a time.
- Prevents Race Conditions.
- Ensures correct data.

---

### join()

- Main thread waits.
- Worker threads finish first.
- Then the remaining code executes.

---

# Memory Trick

```
synchronized

One thread enters.

Others wait.

------------------------

join

Main thread waits.

Worker thread finishes.

Then continue.
```

---

#  Questions

## Why use synchronized?

To prevent multiple threads from updating shared data simultaneously and avoid race conditions.

---

## Why use join()?

To make the current thread wait until another thread finishes execution.

---

## What is the shared resource in this program?

```
CakeCounter Object

counter
```

Both Team A and Team B access the same `counter` variable.

---

#  Definition

> **`synchronized` protects shared resources by allowing only one thread to access them at a time, while `join()` makes one thread wait until another thread completes its execution.**

---


# Whenever you see a multithreading program, ask yourself these **three questions**:

```text
1. How many threads are running?

2. Are they sharing the same object?

3. Do I need synchronized or join?
```

For **your program**:

* ✅ Threads = **2** (`teamA`, `teamB`)
* ✅ Shared Object = **1** (`CakeCounter`)
* ✅ Shared Data = **counter**
* ✅ `synchronized` = Protects `counter`
* ✅ `join()` = Makes the main thread wait before printing

If you follow these three questions for every multithreading example, you'll rarely get confused. This is exactly how experienced Java developers analyze concurrent code. 🚀
