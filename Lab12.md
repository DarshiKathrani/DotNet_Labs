# Lab 12 - CRUD Operations using GridView and SQL Server

## Objective

Learn:

* SQL Server Database
* Tables
* CRUD Operations
* Connection String
* SqlConnection
* SqlCommand
* SqlDataAdapter
* DataTable
* GridView

---

# What is CRUD?

CRUD means:

```text
C → Create

R → Read

U → Update

D → Delete
```

Example:

Student Management System

* Add Student
* Display Student
* Update Student
* Delete Student

---

# Step 1 : Create Database

Open SQL Server Management Studio (SSMS)

Create Database:

```sql
CREATE DATABASE StudentDB;
```

Select Database:

```sql
USE StudentDB;
```

---

# Step 2 : Create Student Table

```sql
CREATE TABLE Student
(
    EnrollmentNo VARCHAR(20),
    StudentName VARCHAR(50),
    Semester INT,
    SPI DECIMAL(4,2),
    CPI DECIMAL(4,2)
);
```

---

# Step 3 : Insert Sample Data

```sql
INSERT INTO Student
VALUES
('230101','Rahul',5,8.50,8.20);
```

```sql
INSERT INTO Student
VALUES
('230102','Priya',5,9.10,8.90);
```

Verify Data:

```sql
SELECT * FROM Student;
```

---

# ASP.NET and SQL Server Architecture

```text
User

 ↓

ASP.NET Page

 ↓

SQL Connection

 ↓

Database

 ↓

Table

 ↓

GridView
```

---

# Connection String

Stored inside:

```text
web.config
```

Example:

```xml
<connectionStrings>

<add
name="constr"
connectionString="Server=.;
Database=StudentDB;
Trusted_Connection=True;" />

</connectionStrings>
```

Purpose:

```text
Tells ASP.NET

Which Database

Should Be Connected
```

---

# SqlConnection

Purpose:

```text
Connect ASP.NET
With SQL Server
```

Syntax:

```csharp
SqlConnection con =
new SqlConnection(connectionString);
```

Think:

```text
ASP.NET ---- ROAD ---- SQL Server
```

SqlConnection creates that road.

---

# Opening Connection

```csharp
con.Open();
```

Meaning:

```text
Start Communication
With Database
```

---

# Closing Connection

```csharp
con.Close();
```

Meaning:

```text
Stop Communication
```

---

# SqlCommand

Purpose:

```text
Execute SQL Query
```

Syntax:

```csharp
SqlCommand cmd =
new SqlCommand(query, con);
```

Example:

```csharp
SqlCommand cmd =
new SqlCommand(
"SELECT * FROM Student",
con
);
```

Think:

```text
SqlConnection
Creates Road

SqlCommand
Carries Message
```

---

# ExecuteNonQuery()

Used For:

```text
INSERT

UPDATE

DELETE
```

Syntax:

```csharp
cmd.ExecuteNonQuery();
```

Memory Trick:

```text
No Data Returned

Only Action Performed
```

---

# ExecuteReader()

Used For:

```text
SELECT
```

Syntax:

```csharp
SqlDataReader dr =
cmd.ExecuteReader();
```

Purpose:

```text
Read Rows
One By One
```

---

# SqlDataAdapter

Most Important for GridView.

Purpose:

```text
Fetch Data
From Database
```

Syntax:

```csharp
SqlDataAdapter da =
new SqlDataAdapter(query, con);
```

Example:

```csharp
SqlDataAdapter da =
new SqlDataAdapter(
"SELECT * FROM Student",
con
);
```

---

# DataTable

Purpose:

```text
Temporarily Store Data
In Memory
```

Syntax:

```csharp
DataTable dt =
new DataTable();
```

Think:

```text
Temporary Table
Inside Application
```

---

# Filling DataTable

```csharp
da.Fill(dt);
```

Flow:

```text
Database

↓

DataAdapter

↓

DataTable
```

---

# GridView

Purpose:

```text
Display Data
In Table Format
```

Syntax:

```aspx
<asp:GridView
ID="gvStudent"
runat="server">
</asp:GridView>
```

Output:

```text
--------------------------------

EnrollmentNo

StudentName

Semester

SPI

CPI

--------------------------------
```

---

# Data Binding

Give Data To GridView:

```csharp
gvStudent.DataSource = dt;
```

Display Data:

```csharp
gvStudent.DataBind();
```

Meaning:

```text
DataSource

↓

DataBind()

↓

Output
```

---

# Complete Display Flow

```csharp
SqlDataAdapter da =
new SqlDataAdapter(query, con);

DataTable dt =
new DataTable();

da.Fill(dt);

gvStudent.DataSource = dt;

gvStudent.DataBind();
```

Visual Flow:

```text
Database

↓

SqlDataAdapter

↓

DataTable

↓

GridView

↓

Output
```

---

# Page_Load()

Very Important Event.

Syntax:

```csharp
protected void Page_Load(
object sender,
EventArgs e)
{

}
```

Purpose:

```text
Runs Whenever
Page Loads
```

Usually Used For:

```text
Display Data

Bind GridView
```

---

# Button Click Event

Syntax:

```csharp
protected void btnSave_Click(
object sender,
EventArgs e)
{

}
```

Purpose:

```text
Runs
When Button Clicked
```

Usually Used For:

```text
Insert

Update

Delete
```

Operations.

---

# Insert Flow

User Enters:

```text
Rahul

5

8.5
```

Flow:

```text
TextBoxes

↓

Button Click

↓

INSERT Query

↓

SqlCommand

↓

ExecuteNonQuery()

↓

Database
```

---

# Read Flow

```text
Page Load

↓

SELECT Query

↓

SqlDataAdapter

↓

DataTable

↓

GridView

↓

Display Data
```

---

# Update Flow

```text
GridView

↓

Edit

↓

Update Query

↓

ExecuteNonQuery()

↓

Database
```

---

# Delete Flow

```text
GridView

↓

Delete Button

↓

DELETE Query

↓

ExecuteNonQuery()

↓

Database
```

---

# Student Entity

Attributes:

* Enrollment No
* Student Name
* Semester
* SPI
* CPI

---

# Product Entity

Attributes:

* Product ID
* Product Name
* Brand ID
* Product Price
* Product Quantity

---

# Mapping Concepts to Practical

| Practical Requirement | Concept                      |
| --------------------- | ---------------------------- |
| Insert Record         | SqlCommand + ExecuteNonQuery |
| Display Records       | SqlDataAdapter + GridView    |
| Update Record         | UPDATE Query                 |
| Delete Record         | DELETE Query                 |
| Display Data          | DataTable + DataBind         |
| Database Connection   | SqlConnection                |

---

# Most Important Viva Questions

### What is SqlConnection?

Used to connect ASP.NET with SQL Server.

---

### What is SqlCommand?

Used to execute SQL queries.

---

### What is SqlDataAdapter?

Used to fetch data from database.

---

### What is DataTable?

Temporary storage for database records.

---

### What is GridView?

Used to display records in tabular format.

---

### What is DataBind()?

Displays data in controls like GridView.

---

### Difference Between ExecuteNonQuery() and ExecuteReader()

| ExecuteNonQuery()     | ExecuteReader() |
| --------------------- | --------------- |
| INSERT                | SELECT          |
| UPDATE                | SELECT          |
| DELETE                | SELECT          |
| Returns affected rows | Returns records |

---

# Quick Revision

```text
Database

↓

SqlConnection

↓

SqlCommand

↓

SqlDataAdapter

↓

DataTable

↓

GridView

↓

DataBind()
```

Remember this flow and most CRUD programs become easy to understand and implement.
