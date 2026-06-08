# Before Starting Lab 7

## How to Create an ASP.NET Web Form (.aspx)

### Step 1

Open Visual Studio.

---

### Step 2

Open your ASP.NET Web Forms Project.

Example:

```text
ASP_NET_LABS
```

---

### Step 3

Right Click Project

```text
Project
  ↓
Add
  ↓
New Item
```

---

### Step 4

Select:

```text
Web Form
```

---

### Step 5

Provide a name.

Examples:

```text
Calculator.aspx

Registration.aspx

Country.aspx

DynamicPanel.aspx
```

---

### Step 6

Click Add.

Visual Studio automatically creates:

```text
Calculator.aspx
```

and

```text
Calculator.aspx.cs
```

---

# Understanding ASPX and ASPX.CS

## Calculator.aspx

Used for:

```text
Design

UI

Controls
```

Examples:

```aspx
<asp:TextBox></asp:TextBox>

<asp:Button></asp:Button>

<asp:Label></asp:Label>
```

---

## Calculator.aspx.cs

Used for:

```text
Logic

Calculations

Events
```

Examples:

```csharp
Addition

Subtraction

Button Click Code
```

---

# ASP.NET Page Structure

```text
Calculator.aspx
        ↓
UI Design

Calculator.aspx.cs
        ↓
Logic
```

---

# Why Do We Use runat="server" ?

Example:

```aspx
<asp:TextBox
ID="txtNum1"
runat="server">
</asp:TextBox>
```

Question:

Why do we write:

```aspx
runat="server"
```

?

Without it:

```text
ASP.NET Cannot Access
The Control
```

With it:

```text
Control Becomes
Available In C#
```

Example:

```csharp
txtNum1.Text
```

works only because:

```aspx
runat="server"
```

is present.

---

# Memory Trick

```text
runat="server"

Means

This Control
Can Be Accessed
From C#
```

---

# Understanding ID Property

Example:

```aspx
<asp:TextBox
ID="txtName"
runat="server">
</asp:TextBox>
```

Purpose:

```text
Unique Name
Of Control
```

Used inside C#:

```csharp
txtName.Text
```

---

# What Does .Text Mean?

Example:

```csharp
txtName.Text
```

Meaning:

```text
Value Stored
Inside TextBox
```

If user enters:

```text
Rahul
```

then:

```csharp
txtName.Text
```

contains:

```text
Rahul
```

---

# Understanding Events

Example:

```aspx
<asp:Button
ID="btnAdd"
runat="server"
Text="Add"
OnClick="btnAdd_Click" />
```

Question:

What happens when button is clicked?

Answer:

```text
btnAdd_Click()
Method Executes
```

---

# Understanding Function Parameters

Example:

```csharp
protected void btnAdd_Click(
object sender,
EventArgs e)
{

}
```

Students usually memorize this without understanding.

Let's break it.

---

## protected

Means:

```text
Method Can Be Used
Inside Current Class
```

---

## void

Means:

```text
Returns Nothing
```

---

## btnAdd_Click

Method Name.

Executed when:

```text
Add Button Clicked
```

---

## object sender

Represents:

```text
Which Control
Triggered The Event
```

Example:

```text
Button Clicked
```

Then sender refers to:

```text
Button Object
```

---

## EventArgs e

Contains information about the event.

Think:

```text
Event Information
Container
```

For most beginner programs:

```text
We Don't Use It
Directly
```

But ASP.NET provides it automatically.

---

# Easy Memory Trick

```csharp
protected void btnAdd_Click(
object sender,
EventArgs e)
```

Read as:

```text
When Add Button Is Clicked

Run This Method
```

That's enough for Lab-7.

---

# Common Controls Used in Lab 7

## Label

Display Text

```aspx
<asp:Label
ID="lblResult"
runat="server">
</asp:Label>
```

---

## TextBox

Take Input

```aspx
<asp:TextBox
ID="txtName"
runat="server">
</asp:TextBox>
```

---

## Button

Perform Action

```aspx
<asp:Button
ID="btnSubmit"
runat="server"
Text="Submit" />
```

---

## CheckBoxList

Multiple Selection

```aspx
<asp:CheckBoxList
ID="cblCountry"
runat="server">
</asp:CheckBoxList>
```

---

## DropDownList

Single Selection

```aspx
<asp:DropDownList
ID="ddlCount"
runat="server">
</asp:DropDownList>
```

---

## Panel

Container For Controls

```aspx
<asp:Panel
ID="pnlDynamic"
runat="server">
</asp:Panel>
```

---

# Complete Request Flow

```text
User Enters Data

↓

TextBox

↓

Button Click

↓

btnSubmit_Click()

↓

Process Data

↓

Display Result
```

Remember this flow and ASP.NET Web Forms become much easier to understand.
