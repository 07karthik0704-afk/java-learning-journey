## What is synchronized?

> **The `synchronized` keyword allows only one thread at a time to execute a critical section of code.**

It prevents multiple threads from modifying the same shared data simultaneously, avoiding **Race Conditions**.

---

# Problem (Without synchronized)

Suppose we have a Bank Account.

```java
class Bank {

    int balance = 1000;

    void withdraw(int amount) {

        System.out.println(Thread.currentThread().getName() + " is withdrawing...");

        balance = balance - amount;

        System.out.println("Balance = " + balance);
    }
}
```

---

## Customer Class

```java
class Customer extends Thread {

    Bank bank;

    Customer(Bank bank, String name) {
        this.bank = bank;
        setName(name);
    }

    @Override
    public void run() {
        bank.withdraw(500);
    }
}
```

---

## Main Class

```java
class FirstProgram {

    public static void main(String[] args) {

        Bank bank = new Bank();

        Customer c1 = new Customer(bank, "Tony");
        Customer c2 = new Customer(bank, "Steve");

        c1.start();
        c2.start();
    }
}
```

---

# What happens?

Initial Balance

```
1000
```

Tony withdraws ₹500.

Steve also withdraws ₹500.

Since both threads access the **same Bank object** at the same time, both may read and update the balance simultaneously.

This can produce inconsistent results.

Example Output

```
Steve is withdrawing...
Tony is withdrawing...
Balance = 0
Balance = 500
```

The output order is unpredictable because both threads are executing concurrently.

This problem is called a **Race Condition**.

---

# Solution (Using synchronized)

```java
class Bank {

    int balance = 1000;

    synchronized void withdraw(int amount) {

        System.out.println(Thread.currentThread().getName() + " is withdrawing...");

        balance = balance - amount;

        System.out.println("Balance = " + balance);
    }
}
```

---

# What changes?

Now only **one thread** can enter the `withdraw()` method at a time.

If another thread tries to enter, it must wait until the current thread finishes.

Execution becomes:

```
Tony
   │
LOCK 🔒
   │
Withdraw ₹500
   │
Balance = 500
   │
Unlock 🔓
   │
--------------------

Steve
   │
LOCK 🔒
   │
Withdraw ₹500
   │
Balance = 0
   │
Unlock 🔓
```

Now the balance is always correct.

---

# Real-Life Example

Imagine there is only **one ATM**.

Without synchronized:

```
Tony enters ATM
Steve also enters ATM 😱
```

Both use the ATM at the same time.

This causes confusion.

---

With synchronized:

```
Tony
   │
Uses ATM
   │
Leaves
   │
----------------
Steve
   │
Uses ATM
```

Only one person uses the ATM at a time.

---

# Memory Trick

```
Without synchronized

Everyone enters together ❌

----------------------------

With synchronized

One enters.

Others wait.

Then next enters. ✅
```

---

# Key Points

- `synchronized` protects **shared data**.
- Only one thread can execute the synchronized method at a time.
- Other threads wait until the lock is released.
- Prevents **Race Conditions**.
- Ensures data consistency.

---

# Definition

> **The `synchronized` keyword allows only one thread at a time to access a critical section of code, preventing race conditions and ensuring correct and consistent data.**
