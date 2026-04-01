## Basic Concepts

### Operators and Operands

* Operator → performs an action
* Operand → the value on which the action is performed

#### Example:

```java id="r4k9dm"
int result = 10 + 5;
```

* `+` → operator
* `10`, `5` → operands

---

## System.out.println()

* `System` is a predefined class in Java (from `java.lang` package)
* It contains a static variable called `out`
* `out` is an object of `PrintStream` class
* Using `out`, we can call the `println()` method

### Flow

System (class) → out (PrintStream object) → println() (method)

#### Example:

```java id="u7h2qp"
System.out.println("Hello World");
```

---

## Naming Convention (Camel Case)

* Java follows **camelCase naming convention**

### Rules

* First word starts with lowercase
* Next words start with uppercase

#### Examples

* Variable → `myName`
* Method → `printDetails()`
* Class → `StudentData` (PascalCase)

---

## My Understanding

Operators perform actions on operands.
`System.out.println()` works by accessing the `out` object of the `System` class, which uses the `PrintStream` class to print output.
Java uses camelCase for naming variables and methods, making code more readable.

---

## Conditional Statements in Java

* Used to control the flow of execution based on conditions

---

## Types of Conditional Statements

### 1. if Statement

* Used to execute code when a condition is true

### 2. if-else Statement

* Executes one block if true, another if false

### 3. else-if Ladder

* Used when multiple conditions need to be checked

---

## Switch Statement

* Used to select one option from multiple cases based on a value

### Example:

```java id="d4m8qs"
int day = 2;

switch(day) {
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    default:
        System.out.println("Invalid");
}
```

---

## When to Use if vs switch

### Use if / else-if when:

* Conditions involve ranges (example: marks > 90)
* Complex logical expressions (example: a > b && b < c)
* Multiple different conditions

---

### Use switch when:

* You are checking a single variable
* Comparing with fixed constant values
* Code becomes cleaner than multiple if-else

---

## Data Types Supported in switch

* `byte`
* `short`
* `int`
* `char`
* `String` (from Java 7)
* `enum`

---

## My Understanding

Conditional statements help control program flow.
`if-else` is useful for complex conditions, while `switch` is better for checking a single value against multiple fixed options.

---

## 💥 Simple Understanding

* if = thinking (conditions, logic)
* switch = choosing (one value, many options)

---

## ⚡ Example Clarity

### Using if:

```java id="h7k2zn"
if (marks > 90)
```

### Using switch:

```java id="q9x5lp"
switch(day)
```

---

## 🧠 Other Names for Conditional Statements

Conditional statements are also known as:

### 1. Decision-Making Statements

* Because they help the program make decisions

### 2. Control Statements

* Because they control the flow of execution

### 3. Selection Statements

* Because they select one path among multiple options

---

## Iterative Statements (Loops)

* Iterative statements are used to repeat a block of code multiple times

---

## Types of Loops

### 1. for Loop

* Used when the number of iterations is known

#### Example:

```java id="f1k9zs"
for(int i = 1; i <= 5; i++) {
    System.out.println(i);
}
```

---

### 2. while Loop (Entry-Control Loop)

* Condition is checked before execution
* If condition is false, loop will not execute

#### Example:

```java id="w3m7qp"
int i = 1;

while(i <= 5) {
    System.out.println(i);
    i++;
}
```

---

### 3. do-while Loop (Exit-Control Loop)

* Condition is checked after execution
* Loop executes at least once even if condition is false

#### Example:

```java id="d8x2vn"
int i = 1;

do {
    System.out.println(i);
    i++;
} while(i <= 5);
```

---

## Key Difference

* **while loop** → checks condition first (may not run)
* **do-while loop** → runs first, then checks condition (runs at least once)

---

## 💥 Quick Clarity

* while = check first → run later
* do-while = run first → check later

---

## My Understanding

Iterative statements are used to repeat code.
`for` loop is used when iterations are known, `while` loop checks condition before execution, and `do-while` ensures the loop runs at least once.

---

## Jump Statements in Java

* Jump statements are used to **alter the normal flow of execution**

---

## Types of Jump Statements

### 1. break Statement

* Used to **terminate the loop or switch statement immediately**
* Control moves outside the loop

#### Example:

```java id="b1x9kp"
for(int i = 1; i <= 5; i++) {
    if(i == 3) {
        break;
    }
    System.out.println(i);
}
```

### Output:

```text id="o7m2qs"
1
2
```

---

### 2. continue Statement

* Used to **skip the current iteration**
* Loop continues with the next iteration

#### Example:

```java id="c4z8dn"
for(int i = 1; i <= 5; i++) {
    if(i == 3) {
        continue;
    }
    System.out.println(i);
}
```

### Output:

```text id="l9v5wr"
1
2
4
5
```

---

## Key Difference

* `break` → stops the loop completely
* `continue` → skips one iteration and continues

---

## 💥 Quick Clarity

* break = exit loop
* continue = skip and move next

---

## My Understanding

Jump statements control the flow by interrupting normal execution.
`break` exits the loop entirely, while `continue` skips the current iteration and continues with the next one.

---

## Arrays in Java

* Arrays are used to store multiple values of the same data type
* All elements in an array must be of the same type

---

## Declaration and Initialization

```java id="n4x7kp"
int[] rollno = new int[20];
```

* `int[]` → array type
* `rollno` → array name (identifier)
* `new int[20]` → creates an array of size 20

---

## Default Values

* When an array is created, default values are assigned automatically

| Data Type | Default Value             |
| --------- | ------------------------- |
| int       | 0                         |
| float     | 0.0                       |
| double    | 0.0                       |
| boolean   | false                     |
| char      | '\u0000' (null character) |
| object    | null                      |

---

## Example

```java id="y6p2qd"
int[] rollno = new int[3];

System.out.println(rollno[0]); // 0
System.out.println(rollno[1]); // 0
System.out.println(rollno[2]); // 0
```

---

## My Understanding

Arrays are used to store multiple values of the same data type in a single variable.
When created, Java automatically assigns default values to all elements.

---

