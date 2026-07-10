# Lab-4 : Arrays and Strings in C#

---

# Arrays in C#

## What is an Array?

An **Array** is a collection of elements of the **same data type** stored in contiguous memory locations.

Instead of creating multiple variables, we can store multiple values in a single array.

Example:

```
Marks = 85, 90, 78, 95, 88
```

Instead of

```csharp
int m1 = 85;
int m2 = 90;
int m3 = 78;
...
```

we use

```csharp
int[] marks = {85,90,78,95,88};
```

---

# Array Declaration

Syntax

```csharp
datatype[] arrayName;
```

Example

```csharp
int[] numbers;
string[] names;
char[] letters;
double[] salary;
```

---

# Array Initialization

## Method 1

```csharp
int[] numbers = new int[5];
```

Creates an array of size 5.

Default values

```
int -> 0
double -> 0
char -> '\0'
string -> null
bool -> false
```

---

## Method 2

```csharp
int[] numbers = {10,20,30,40,50};
```

Compiler automatically calculates the size.

---

## Method 3

```csharp
int[] numbers = new int[] {10,20,30,40,50};
```

---

# Dynamic Array Input

```csharp
Console.Write("Enter Size : ");
int n = Convert.ToInt32(Console.ReadLine());

int[] arr = new int[n];

for(int i=0;i<n;i++)
{
    arr[i]=Convert.ToInt32(Console.ReadLine());
}
```

Input

```
5

10
20
30
40
50
```

---

# Accessing Array Elements

Index always starts from **0**

Example

```csharp
int[] arr = {10,20,30,40};

Console.WriteLine(arr[0]);
Console.WriteLine(arr[2]);
```

Output

```
10
30
```

---

# Traversing an Array using for loop

```csharp
for(int i=0;i<arr.Length;i++)
{
    Console.WriteLine(arr[i]);
}
```

Output

```
10
20
30
40
```

---

# Traversing an Array using foreach

```csharp
foreach(int num in arr)
{
    Console.WriteLine(num);
}
```

Output

```
10
20
30
40
```

---

# Array Length Property

Returns total number of elements.

```csharp
int[] arr={10,20,30,40};

Console.WriteLine(arr.Length);
```

Output

```
4
```

---

# Finding Sum of Array

```csharp
int sum=0;

for(int i=0;i<arr.Length;i++)
{
    sum+=arr[i];
}

Console.WriteLine(sum);
```

---

# Finding Maximum Number

```csharp
int max=arr[0];

for(int i=1;i<arr.Length;i++)
{
    if(arr[i]>max)
        max=arr[i];
}

Console.WriteLine(max);
```

---

# Finding Minimum Number

```csharp
int min=arr[0];

for(int i=1;i<arr.Length;i++)
{
    if(arr[i]<min)
        min=arr[i];
}

Console.WriteLine(min);
```

---

# Counting Even and Odd Numbers

```csharp
int even=0;
int odd=0;

foreach(int num in arr)
{
    if(num%2==0)
        even++;
    else
        odd++;
}
```

---

# Common Array Properties

| Property | Description |
|-----------|-------------|
| Length | Returns size of array |
| Rank | Returns dimensions |
| Clone() | Creates copy |
| CopyTo() | Copies array |
| Reverse() | Reverse array |
| Sort() | Sort array |

---

# Array.Sort()

Sorts array in ascending order.

```csharp
int[] arr={40,10,30,20};

Array.Sort(arr);
```

Output

```
10
20
30
40
```

---

# Array.Reverse()

```csharp
Array.Reverse(arr);
```

Output

```
40
30
20
10
```

---

# String in C#

## What is String?

A **String** is a sequence of characters enclosed inside double quotes.

Example

```csharp
string name="Darshan";
```

---

# String Declaration

```csharp
string name;
```

---

# String Initialization

```csharp
string city="Rajkot";
```

---

# Reading String

```csharp
string name=Console.ReadLine();
```

---

# String Length

Returns total number of characters.

```csharp
string name="Darshan";

Console.WriteLine(name.Length);
```

Output

```
7
```

---

# String Methods

---

# Contains()

Checks whether a substring exists.

Syntax

```csharp
string.Contains(string)
```

Example

```csharp
string str="Darshan University";

Console.WriteLine(str.Contains("University"));
```

Output

```
True
```

---

# StartsWith()

Checks beginning of string.

```csharp
string str="Darshan University";

Console.WriteLine(str.StartsWith("Dar"));
```

Output

```
True
```

---

# EndsWith()

Checks ending of string.

```csharp
Console.WriteLine(str.EndsWith("University"));
```

Output

```
True
```

---

# Equals()

Checks whether both strings are exactly equal.

```csharp
string s1="ABC";
string s2="ABC";

Console.WriteLine(s1.Equals(s2));
```

Output

```
True
```

---

# CompareTo()

Compares two strings alphabetically.

Returns

```
0  -> Equal

Positive -> First string greater

Negative -> Second string greater
```

Example

```csharp
string s1="Cat";
string s2="Dog";

Console.WriteLine(s1.CompareTo(s2));
```

Output

```
Negative Value
```

---

# IndexOf()

Returns first occurrence.

```csharp
string str="Programming";

Console.WriteLine(str.IndexOf('r'));
```

Output

```
1
```

---

# LastIndexOf()

Returns last occurrence.

```csharp
Console.WriteLine(str.LastIndexOf('r'));
```

Output

```
4
```

---

# Replace()

Replaces character or string.

```csharp
string str="Programming";

Console.WriteLine(str.Replace('r','D'));
```

Output

```
PDogDamming
```

---

# Trim()

Removes spaces from beginning and end.

```csharp
string str="   Hello   ";

Console.WriteLine(str.Trim());
```

Output

```
Hello
```

---

# ToUpper()

Converts string into uppercase.

```csharp
string str="darshan";

Console.WriteLine(str.ToUpper());
```

Output

```
DARSHAN
```

---

# ToLower()

Converts string into lowercase.

```csharp
string str="DARSHAN";

Console.WriteLine(str.ToLower());
```

Output

```
darshan
```

---

# Substring()

Extracts part of string.

Syntax

```csharp
Substring(StartIndex)

Substring(StartIndex,Length)
```

Example

```csharp
string str="Programming";

Console.WriteLine(str.Substring(3));
```

Output

```
gramming
```

Example

```csharp
Console.WriteLine(str.Substring(3,4));
```

Output

```
gram
```

---

# Remove()

Removes characters.

```csharp
string str="Programming";

Console.WriteLine(str.Remove(3,4));
```

Output

```
Proming
```

---

# Insert()

Inserts string at a specified index.

```csharp
string str="Programming";

Console.WriteLine(str.Insert(3,"ABC"));
```

Output

```
ProABCgramming
```

---




# Escape Characters

| Escape | Meaning |
|---------|----------|
| \n | New Line |
| \t | Tab |
| \\ | Backslash |
| \" | Double Quote |
| \' | Single Quote |

Example

```csharp
Console.WriteLine("Hello\nWorld");
```

Output

```
Hello
World
```

---

# Difference between Equals() and CompareTo()

| Equals() | CompareTo() |
|------------|-------------|
| Checks equality | Compares alphabetically |
| Returns True/False | Returns Integer |
| Used to check same strings | Used for sorting/comparison |

Example

```csharp
ABC
ABC

Equals() -> True

CompareTo() -> 0
```

Example

```csharp
Apple
Ball

Equals() -> False

CompareTo() -> Negative
```

---

# Lab-4 Important Methods

## Array

- Length
- Sort()
- Reverse()

## String

- Contains()
- Equals()
- CompareTo()
- IndexOf()
- LastIndexOf()
- Replace()
- Trim()
- Substring()
- ToUpper()
- ToLower()
- StartsWith()
- EndsWith()
- Insert()
- Remove()

