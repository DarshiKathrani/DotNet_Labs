# Java Lab 1 - Fundamentals Revision

## Objective

Before solving the lab programs, revise the Java concepts required to solve them independently.

---

# 1. Variables and Input

A variable is used to store data.

Examples:

* Age = 20
* Name = "Rahul"
* Marks = 85

## Common Data Types

| Data Type | Example |
| --------- | ------- |
| int       | 10      |
| double    | 10.5    |
| char      | 'A'     |
| String    | "Hello" |
| boolean   | true    |

## Scanner (Input)

To take input from the user:

```java
Scanner sc = new Scanner(System.in);
```

Integer Input:

```java
int n = sc.nextInt();
```

Decimal Input:

```java
double d = sc.nextDouble();
```

String Input:

```java
String name = sc.next();
```

## Think

If the user wants to add two numbers:

* Where will the first number be stored?
* Where will the second number be stored?
* Where will the result be stored?

---

# 2. Decision Making (if-else)

Programs often need to make decisions.

Examples:

* If marks >= 35 → Pass
* Else → Fail

## Syntax

```java
if(condition)
{
}
else
{
}
```

## Comparison Operators

| Operator | Meaning               |
| -------- | --------------------- |
| >        | Greater Than          |
| <        | Less Than             |
| >=       | Greater Than or Equal |
| <=       | Less Than or Equal    |
| ==       | Equal To              |
| !=       | Not Equal To          |



# 3. Loops

Loops are used when we need to repeat a task.

Example:

Print numbers from 1 to 100.

Writing 100 print statements is not practical.

## for Loop Syntax

```java
for(initialization; condition; increment)
{
}
```

Example:

```java
for(int i=1;i<=5;i++)
{
}
```

## Dry Run

For:

```java
for(int i=1;i<=5;i++)
{
}
```

Fill the table:

| i |
| - |
| 1 |
| 2 |
| 3 |
| 4 |
| 5 |

How many times will the loop execute?

---

# 4. Arrays

Suppose you want to store marks of 100 students.

Creating variables like:

```text
marks1
marks2
marks3
...
marks100
```

is not practical.

Arrays allow us to store multiple values together.

## Declaration

```java
int arr[] = new int[5];
```

## Accessing Elements

```java
arr[0]
arr[1]
arr[2]
```

## Traversing an Array

```java
for(int i=0;i<arr.length;i++)
{
}
```

## Example

Values:

```text
10 20 30 40 50
```

Indexes:

```text
0 1 2 3 4
```


---

# 5. Two-Dimensional Arrays (Matrices)

A matrix is like a table.

Example:

```text
1 2 3
4 5 6
7 8 9
```

Rows = 3

Columns = 3

## Declaration

```java
int matrix[][] = new int[3][3];
```

## Traversing a Matrix

```java
for(int i=0;i<3;i++)
{
    for(int j=0;j<3;j++)
    {
    }
}
```

## Activity

Matrix A:

```text
1 2
3 4
```

Matrix B:

```text
5 6
7 8
```

How would you add them?

Answer:

Add corresponding elements.

---

# 6. Classes and Objects

## Why Do We Need Classes?

Imagine we want to store information about a student.

Every student has:

* ID
* Name
* Age

We can create variables:

```java
int id;
String name;
int age;
```

Now imagine we have 100 students.

Managing separate variables becomes difficult.

To organize related data together, Java provides Classes.

---

## What is a Class?

A class is a blueprint or template.

Think of it as a form.

Example:

```text
Student Form

ID : ______

Name : ______

Age : ______
```

The form itself is not a student.

It only describes what information a student should have.

### Syntax

```java
class ClassName
{
}
```

Example:

```java
class Student
{
    int id;
    String name;
    int age;
}
```

This only describes a Student.

No actual student exists yet.

---

## What is an Object?

An object is an actual instance of a class.

Class:

```text
Student
```

Objects:

```text
Rahul
Priya
Amit
```

Each student has different values.

Example:

```text
Rahul

ID = 101
Name = Rahul
Age = 18
```

```text
Priya

ID = 102
Name = Priya
Age = 19
```

---

## Class vs Object

| Class     | Object     |
| --------- | ---------- |
| Blueprint | Real Thing |
| Student   | Rahul      |
| Car       | Honda City |
| Mobile    | Samsung    |

---

## Data Members

Variables declared inside a class are called data members.

Example:

```java
class Student
{
    int id;
    String name;
    int age;
}
```

Here:

* id
* name
* age

are data members.

---

## Methods

Methods define actions that an object can perform.

### Syntax

```java
returnType methodName()
{
}
```

Example:

```java
void display()
{
}
```

---

## Class with Data Members and Methods

```java
class Student
{
    int id;
    String name;

    void getData()
    {
    }

    void display()
    {
    }
}
```

---

## Creating an Object

### Syntax

```java
ClassName objectName = new ClassName();
```

Example:

```java
Student s = new Student();
```

Breakdown:

```text
Student
↓
Class Name

s
↓
Object Name

new Student()
↓
Creates Object
```

---

## Accessing Data Members

### Syntax

```java
objectName.variableName
```

Example:

```java
s.id
s.name
```

---

## Calling Methods

### Syntax

```java
objectName.methodName();
```

Example:

```java
s.display();
```

---

## Complete Flow

```text
Create Class
      ↓
Create Data Members
      ↓
Create Methods
      ↓
Create Object
      ↓
Call Methods
```

---

# Mapping Concepts to Lab Questions

| Question              | Concept            |
| --------------------- | ------------------ |
| Addition of 2 numbers | Variables, Input   |
| Maximum of 3 numbers  | if-else            |
| Leap Year             | if-else, Operators |
| Factorial             | Loop               |
| Prime Number          | Loop, Conditions   |
| Max & Min from Array  | Arrays             |
| Matrix Addition       | 2D Arrays          |
| Candidate Class       | Classes & Objects  |

---





