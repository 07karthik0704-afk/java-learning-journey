# File Handling (Java)

## What is File Handling?

> **File Handling is used to read data from a file and write data into a file.**

### Why do we need File Handling?

Normally, a Java program gets data from:

1. User Input (Keyboard)
2. File

Examples:
- Student Records
- Employee Details
- Configuration Files
- Logs
- CSV Files

---

# Reading a File

## Steps

### 1. Create a File Object

```java
File f = new File("doc.txt");
```

**Purpose**

- Represents a file.
- Does **not** read or write the file.

---

### 2. Create Scanner Object

```java
Scanner reader = new Scanner(f);
```

**Purpose**

- Reads data from the file.

---

### 3. Read the File

```java
while(reader.hasNextLine()){
    System.out.println(reader.nextLine());
}
```

**Methods**

- `hasNextLine()` → Checks if another line exists.
- `nextLine()` → Reads the next line.

---

### 4. Close Scanner

```java
reader.close();
```

Releases system resources.

---

## Flow

```
doc.txt
    │
    ▼
 File Object
    │
    ▼
 Scanner
    │
    ▼
Read Line by Line
    │
    ▼
Output
```

---

# Writing to a File

## Example

```java
File f = new File("doc.txt");

FileWriter writer = new FileWriter(f);

writer.write("Hello Java");

writer.close();
```

---

## Flow

```
Program
    │
    ▼
FileWriter
    │
    ▼
doc.txt
```

---

## Important Methods

### File

```java
exists()
createNewFile()
delete()
getName()
getAbsolutePath()
length()
```

---

### Scanner

```java
hasNextLine()
nextLine()
```

---

### FileWriter

```java
write()
append()
close()
```

---

# Overwrite vs Append

## Overwrite (Default)

```java
FileWriter writer = new FileWriter(f);
```

Existing file:

```
Tony
```

After writing:

```
Hello
```

Old content is replaced.

---

## Append

```java
FileWriter writer = new FileWriter(f, true);

writer.write("\nHello");
```

Output:

```
Tony
Hello
```

Adds new content without deleting existing data.

---

# Why try-catch?

Reading or writing files may fail because:

- File doesn't exist.
- Invalid path.
- Permission denied.
- Disk full.

Java throws:

```text
FileNotFoundException
IOException
```

These are **Checked Exceptions**, so the compiler forces us to handle them.

Example

```java
try{

}
catch(IOException e){

}
```

---

# Why close()?

```java
reader.close();
writer.close();
```

Purpose:

- Releases system resources.
- Prevents resource leaks.
- Good programming practice.

---

# Important Classes

| Class | Purpose |
|--------|----------|
| File | Represents a file or directory |
| Scanner | Reads data from a file |
| FileWriter | Writes data into a file |

---

# Memory Trick

```
File Handling

Read
----
File
   ↓
Scanner
   ↓
Program

----------------

Write
-----
Program
   ↓
FileWriter
   ↓
File
```

---


## Why do we use File Handling?

To store data permanently and read/write data from files.

---

## What is File?

Represents a file or directory.

It does **not** read or write the file.

---

## Who reads the file?

Scanner

---

## Who writes the file?

FileWriter

---

## Why use try-catch?

Because file operations may throw Checked Exceptions like:

- FileNotFoundException
- IOException

---

## Why use close()?

To release resources after reading or writing.

---

# One-Line  Definition

> **File Handling is the process of reading data from a file and writing data into a file using predefined Java classes such as File, Scanner, and FileWriter.**
