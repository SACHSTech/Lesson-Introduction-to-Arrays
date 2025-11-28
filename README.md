# Introduction to Arrays

Up until now, every program we have written has stored data using **individual variables**:

```java
int mark1;
int mark2;
int mark3;
```

This works for small tasks, but quickly becomes unmanageable. Imagine storing **30 student marks**, or **100 temperatures**, or **5000 pixel values**.  

A program with hundreds of separate variables is not realistic to write, fix, or maintain.

To solve this, Java gives us **arrays**.

An **array** lets us store a **list of items of the same type**, all under one variable name, accessed by a number called an **index**.

```
Index:   0    1    2    3    4
Value:  75   81   67   85   91
```

Arrays allow our programs to scale from tiny examples to real-world workloads.

## Why Arrays?

Consider a program meant to manage marks for a class of 30 students. It must:

- store 30 marks,
- compute the average,
- print any mark upon request.

Before arrays, you would need **30 separate variables**.  
With arrays, you use **one variable** holding **30 elements**.

This is the first example of a true **data structure** — a way of organizing data so programs can process it efficiently.

# What Is an Array?

An array is:

- a **list of values**,  
- all values must have the **same data type**,  
- each value is stored in an **element**,  
- each element is accessed using an **index**,  
- indices start at **0**.

Examples:

- `int[] absences` — list of student absences  
- `double[] temperatures` — list of temperatures  
- `String[] names` — list of names  

Visual:

```
names
 +---------+---------+---------+---------+
 |  "Amy"  | "Chris" | "Holly" |  "Ben"  |
 +---------+---------+---------+---------+
    index 0   index 1   index 2   index 3
```

Accessing:

```java
System.out.println(names[2]); // Holly
```

# Declaring an Array

```java
int[] marks;
String[] names;
double[] menuPrices;
```

Notes:

- The **base type** tells Java what goes inside the list.
- `[]` means “this will store a list”.
- Declaring does not create the list yet.

# Creating an Array

```java
marks = new int[30];
```

Or combined:

```java
int[] marks = new int[30];
```

Another example:

```java
String[] students = new String[5];
```

Each element starts as `0` (for numbers) or `null` (for Strings).

# Default Element Values

- numeric arrays → **0**
- boolean arrays → **false**
- object arrays (String) → **null**

Examples:

```java
int[] scores = new int[4];
// [0, 0, 0, 0]

String[] names = new String[3];
// [null, null, null]
```

# Setting Element Values

```java
marks[0] = 75;
marks[1] = 81;
marks[2] = 67;
```

General pattern:

```
arrayName[index] = value;
```

# Initializing an Array (Array Initializer)

```java
int[] absences = {4, 3, 6, 8, 9};
```

Another example:

```java
int[] daysInMonth = {31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31};
System.out.println(daysInMonth[3]); // April = 30
```

# Accessing Array Elements

```java
System.out.println(marks[2]);
System.out.println(names[0]);
System.out.println(menuPrices[menuPrices.length - 1]);
```

Index may be:

- a literal (`marks[4]`)
- a variable (`marks[i]`)
- an expression (`marks[x+1]`)

Remember:

```
nth element is at index n - 1
```

# Array Length

```java
System.out.println(marks.length);
```

This is critical for loops.

# Full Example

```java
public class Example extends ConsoleProgram {

  public void run() {
    String[] names = new String[5];
    double[] marks = new double[5];

    names[0] = "Gordon";
    names[1] = "Michael";
    names[2] = "Christine";
    names[3] = "Holly";
    names[4] = "Ben";

    marks[0] = 89.9;
    marks[1] = 82.3;
    marks[2] = 91.4;
    marks[3] = 93.6;
    marks[4] = 98.7;

    System.out.println(names[0] + " has a mark of " + marks[0]);

    int[] absences = {4, 3, 6, 8, 9};

    System.out.println(absences[0]);
    System.out.println(absences[absences.length - 1]);
  }
}
```

# Practice Problems

### Problem 1 — First and Last
Create an `int[]` storing cans collected for 5 homerooms.  
Assign values and print the **first** and **last**.

### Problem 2 — Favourite Songs
Create a `String[]` of 5 favourite songs.  
Print the **middle** element.

### Problem 3 — Menu Prices
Create a `double[]` using an initializer containing 6 prices.  
Print the **second-last** price.

### Problem 4 — Replace a Value
```java
int[] nums = {4, 8, 15, 16, 23, 42};
```
Replace index 2 with `99`.  
Print all values.

### Problem 5 — Swap
Create a 5-element integer array.  
Swap the first and last elements.

### Problem 6 — Copy by Index
Copy elements from one `String[]` to another manually with assignment.

### Problem 7 — Index Expressions
Using:

```java
double[] data = {1.5, 3.2, 4.8, 7.6, 9.1};
```

Print:

- first  
- last  
- middle  
- element at `(data.length - 3)`

### Problem 8 — Three Names by User Input
Ask user for three names.  
Store them in a `String[]`.  
Print first, middle, last.

### Problem 9 — Simple Index Math
```java
int[] values = {10, 20, 30, 40, 50};
```

Print:

```
10 + 30 + 50 = 90
```

### Problem 10 — Basic Table (Challenge)
```java
String[] players = {"Ana", "Ben", "Chen", "Dina"};
int[] scores = {14, 22, 18, 31};
```

Print:

```
Ana   : 14
Ben   : 22
Chen  : 18
Dina  : 31
```

Use:

```java
System.out.printf("%-6s : %d\n", players[i], scores[i]);
```