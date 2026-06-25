# Java Fundamentals - How Java Works Internally

## Flow

```text
Java Source Code (.java)
        ↓
javac (Compiler)
        ↓
Bytecode (.class)
        ↓
JVM
        ↓
Machine Code
        ↓
CPU
        ↓
Output
```

## Explanation

* Write the program in a `.java` file.
* `javac` compiles the source code into **Bytecode** (`.class`).
* Bytecode is **platform independent**.
* The **JVM** converts bytecode into **machine code**.
* The **CPU** executes the machine code and produces the output.

## Why is Java Platform Independent?

* Java compiler generates **Bytecode**.
* The same bytecode runs on any operating system with a compatible JVM.
* Only the **JVM is platform dependent**.

**Write Once, Run Anywhere (WORA)**

## Interview Points

* `.java` → Source Code
* `javac` → Compiler
* `.class` → Bytecode
* JVM → Converts Bytecode to Machine Code
* CPU → Executes Machine Code
* Java → Platform Independent
* JVM → Platform Dependent

## Memory Trick

```text
.java
  ↓
javac
  ↓
.class
  ↓
JVM
  ↓
Machine Code
  ↓
CPU
  ↓
Output
```
# Java Fundamentals - JDK (Java Development Kit)

## Definition

**JDK (Java Development Kit)** is a software package used to **develop, compile, and run** Java applications.

## Components

```text
JDK
├── JRE (lib)
│     └── JVM (byte -> machine)
└── Development Tools
      ├── javac
      ├── jar
      ├── javadoc
      └── jdb
```

## Developer vs End User

| Developer                    | End User                    |
| ---------------------------- | --------------------------- |
| Uses **JDK**                 | Uses **JRE** (historically) |
| Can write & compile programs | Can only run Java programs  |

---
# Java Fundamentals - JIT (Just-In-Time) Compiler

## Definition

**JIT (Just-In-Time) Compiler** is a part of the **JVM** that improves Java program performance.

## Flow

```text
Bytecode
    │
    ▼
Interpreter
    │
    ├── Executes Frequently?
    │
    ├── No → Continue Interpreting
    │
    └── Yes
          │
          ▼
     JIT Compiler
          │
          ▼
Native Machine Code (Cached)
          │
          ▼
CPU
```

##

* **JIT = Just-In-Time Compiler**
* Part of the JVM.
* Optimizes frequently executed code.
* Avoids repeated interpretation.
* Makes Java programs run faster.

##

