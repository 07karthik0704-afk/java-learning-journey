## Operators in Java

### Types of Operators

#### 1. Binary Operator

* Works with two values (operands)

#### Example:

```java id="x1a9qd"
int a = 10 + 5;
```

---

#### 2. Unary Operator

* Works with one value

#### Example:

```java id="p3k8zn"
int a = 10;
a++;
```

---

## Arithmetic Operators

* Used to perform mathematical operations

* `+` → Addition

* `-` → Subtraction

* `*` → Multiplication

* `/` → Division

* `%` → Modulus

---

### Important Point

* When two integers are divided, the result will be an integer

#### Example:

```java id="m7q2ls"
int a = 10 / 3;  // Output: 3
```

---

## Type Casting

### Implicit Casting

* Smaller data type → larger data type
* Done automatically

#### Example:

```java id="v5t9bn"
int a = 10;
double b = a;
```

---

### Explicit Casting

* Larger data type → smaller data type
* Done manually

#### Example:

```java id="c8r4yx"
double a = 10.5;
int b = (int) a;
```

---

## Unary Operators

* `++` → Increment
* `--` → Decrement

---

### Pre and Post

#### Pre-Increment:

```java id="h2w6jk"
int a = 5;
int b = ++a;  // a = 6, b = 6
```

#### Post-Increment:

```java id="n9d3qp"
int a = 5;
int b = a++;  // a = 6, b = 5
```

---

## Relational Operators

* Used to compare values

* `<` → Less than

* `>` → Greater than

* `<=` → Less than or equal

* `>=` → Greater than or equal

* `==` → Equal to

* `!=` → Not equal

---

## Logical Operators

* Used to combine conditions

* `&&` → AND

* `||` → OR

* `!` → NOT

---

## My Understanding

Operators help us perform operations on values.
Binary operators work with two values, while unary operators work with one value.
Different types of operators are used for calculations, comparisons, and logical conditions.

---

## Operator Precedence in Java

## 🧠 What is Operator Precedence?

* Operator precedence defines **which operation runs first** when multiple operators are present in an expression

---

## 💡 Real-life Example

In mathematics:

```text
2 + 3 * 4
```

* Multiplication is performed first

```text
3 * 4 = 12  
2 + 12 = 14
```

* Same concept applies in Java

---

## ⚡ Example in Java

```java id="k3f9dn"
int result = 10 + 5 * 2;
```

### Step-by-step:

```text
5 * 2 = 10  
10 + 10 = 20
```

✔️ Final Answer = **20**

---

## 🔥 Basic Precedence Order (High → Low)

1. `()` → Brackets
2. `++ --` → Unary
3. `* / %` → Arithmetic
4. `+ -` → Arithmetic
5. `< > <= >=` → Relational
6. `== !=` → Equality
7. `&&` → Logical AND
8. `||` → Logical OR

---

## 💥 Important Rule

* Use **brackets `()`** to control execution order

---

## Example with Brackets

```java id="t7v2xm"
int result = (10 + 5) * 2;
```

### Step-by-step:

```text
10 + 5 = 15  
15 * 2 = 30
```

✔️ Final Answer = **30**

---

## 🧠 Memory Trick

* Brackets
* Unary
* Multiply / Divide
* Add / Subtract
* Comparisons
* Logical operators

---

## 💥 Real Dev Tip

* Even if you know precedence:

  * Always use brackets for clarity
  * Improves readability
  * Helps avoid bugs

---

## Operator Associativity in Java

## 🧠 What Happens When Operators Have Same Precedence?

* When operators have the **same precedence**, Java follows **associativity**

---

## ⚡ Rule

* Most operators follow:
  **Left → Right (Left-to-Right associativity)**

---

## 💡 Example

```java id="a7m2kx"
int result = 10 - 5 - 2;
```

### Step-by-step:

```text id="z3v9qn"
10 - 5 = 5  
5 - 2 = 3
```

✔️ Final Answer = **3**

* Evaluation happens from **left to right**

---

## ⚠️ Important Exception

* Some operators follow:
  **Right → Left associativity**

### Example:

```java id="l8p4dt"
int a = b = 10;
```

### Step-by-step:

```text id="w2k6rb"
b = 10  
a = b
```

✔️ Evaluation happens from **right to left**

---

## 💥 Easy Rule to Remember

* Same precedence:

  * Mostly → **Left to Right**
  * Assignment (`=`) → **Right to Left**

---

## 🧠 One-line Understanding

If multiple operators have the same precedence, execution follows associativity — usually left to right.


---



## ⚡ One-line Understanding

Operator precedence decides which operation executes first in an expression.

-----
