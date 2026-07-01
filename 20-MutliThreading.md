# Multithreading (Introduction)

## What is a Process?

> **A Process is a program that is currently running.**

### Examples

- MS Word
- Spotify
- Chrome
- VS Code

Each process has its own:
- Memory
- Resources
- Threads

---

# What is a Thread?

> **A Thread is a lightweight unit (path) of execution inside a process.**

A process can have one or more threads.

---

# Why do we need Multithreading?

Without Multithreading:

```
Task 1
   ↓
Task 2
   ↓
Task 3
```

Each task executes one after another.

---

With Multithreading:

```
Task 1   Task 2   Task 3
   │        │        │
   └────────┼────────┘
      Execute Together
```

Multiple tasks execute concurrently, making the application more responsive and utilizing the CPU efficiently.

---

# Real-Life Example

### Cake Shop

```
Cake Shop (Process)

│
├── Mixing Thread
├── Baking Thread
├── Decorating Thread
└── Packing Thread
```

One person doing everything takes more time.

Multiple workers performing different tasks reduce the overall time.

---

# CPU Cores

Earlier:

```
CPU
└── 1 Core
```

Only one thread can execute at a time (rapid switching creates the illusion of multitasking).

Modern CPUs:

```
CPU
├── Core 1
├── Core 2
├── Core 3
├── ...
└── Core 8
```

Multiple cores can execute multiple threads simultaneously, improving performance.

---

# Process vs Thread

| Process | Thread |
|---------|--------|
| Running Program | Small execution unit inside a process |
| Independent | Depends on a process |
| Own memory/resources | Shares process memory/resources |
| Example: Chrome | Example: Download, UI, Auto Save |

---

# Examples

## MS Word (Process)

```
MS Word

├── Typing Thread
├── Grammar Check Thread
├── Spell Check Thread
├── Auto Save Thread
└── Printing Thread
```

All these threads work independently inside the same process.

---

## Spotify (Process)

```
Spotify

├── Music Playing Thread
├── Download Thread
├── Network Thread
└── UI Thread
```

Spotify is a separate process and does not share its threads with MS Word.

---

# Why is Multithreading Useful?

- Improves application performance.
- Executes multiple tasks concurrently.
- Better CPU utilization.
- Makes applications more responsive.

---

# Memory Trick

```
Operating System
        │
        ▼
     Process
        │
        ▼
     Thread(s)
```

Example:

```
Operating System
        │
        ▼
      Chrome
        │
   ┌────┼────┐
   ▼    ▼    ▼
 Tab  Download Video
```

---

# Questions

## What is a Process?

A process is a program that is currently running.

---

## What is a Thread?

A thread is a lightweight unit (path) of execution inside a process.

---

## Why do we need Multithreading?

To execute multiple tasks concurrently, improve responsiveness, and utilize CPU resources efficiently.

---

## Difference Between Process and Thread

| Process | Thread |
|---------|--------|
| Independent program | Execution path inside a process |
| Own memory | Shares process memory |
| Heavyweight | Lightweight |

---

# One-Line Interview Definition

> **Multithreading is the ability of a process to execute multiple threads (tasks) concurrently, improving performance and responsiveness.**
