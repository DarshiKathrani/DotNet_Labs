# ASP.NET Lab 7 - Basic Web Controls Revision

## Objective

Before solving the lab programs, revise the ASP.NET Web Forms controls required for this practical.

---

# What is a Web Form?

A Web Form is a page that allows users to interact with a web application.

Examples:

* Login Form
* Registration Form
* Calculator
* Feedback Form

A Web Form usually contains:

* Labels
* TextBoxes
* Buttons
* Images
* DropDownLists
* CheckBoxLists
* Calendars

---

# ASP.NET Server Controls

ASP.NET provides ready-made controls.

These controls execute on the server and help create dynamic web applications.

Syntax:

```aspx
<asp:ControlName runat="server" />
```

Example:

```aspx
<asp:TextBox runat="server"></asp:TextBox>
```

---

# 1. Label Control

A Label is used to display text.

Example:

```aspx
<asp:Label
    ID="lblName"
    runat="server"
    Text="Enter Name">
</asp:Label>
```

Output:

```text
Enter Name
```

---

# 2. TextBox Control

Used to accept input from the user.

Example:

```aspx
<asp:TextBox
    ID="txtName"
    runat="server">
</asp:TextBox>
```

User enters:

```text
Rahul
```

---

## Accessing TextBox Value

Code Behind:

```csharp
txtName.Text
```

Think:

How will a calculator get numbers from the user?

Answer:

Using TextBoxes.

---

# 3. Button Control

Used to perform an action.

Example:

```aspx
<asp:Button
    ID="btnSubmit"
    runat="server"
    Text="Submit" />
```

Output:

```text
[ Submit ]
```

---

# Button Click Event

When user clicks a button:

```text
Button Click
      ↓
Event Executes
      ↓
Code Runs
```

Syntax:

```csharp
protected void btnSubmit_Click(object sender, EventArgs e)
{
}
```

---

# Complete Flow

```text
User enters data
       ↓
Clicks Button
       ↓
Button Click Event
       ↓
Process Data
       ↓
Display Result
```

---

# 4. HyperLink Control

Used to navigate to another page or website.

Example:

```aspx
<asp:HyperLink
    ID="hlGoogle"
    runat="server"
    Text="Open Google">
</asp:HyperLink>
```

Think:

When user clicks a link, where should they go?

---

# 5. Image Control

Used to display images.

Example:

```aspx
<asp:Image
    ID="imgLogo"
    runat="server" />
```

Common Uses:

* Company Logo
* User Profile
* Product Image

---

# 6. LinkButton Control

Looks like a hyperlink but behaves like a button.

Example:

```aspx
<asp:LinkButton
    ID="lnkSubmit"
    runat="server"
    Text="Click Here">
</asp:LinkButton>
```

Difference:

| HyperLink            | LinkButton        |
| -------------------- | ----------------- |
| Navigation           | Executes Event    |
| No Server Processing | Server Processing |

---

# 7. Calendar Control

Used to select a date.

Example:

```aspx
<asp:Calendar
    ID="calDOB"
    runat="server">
</asp:Calendar>
```

Common Uses:

* Date of Birth
* Appointment Date
* Event Date

---

# 8. DropDownList Control

Used to select one option from many.

Example:

```aspx
<asp:DropDownList
    ID="ddlCountry"
    runat="server">
</asp:DropDownList>
```

Output:

```text
▼ India
```

Examples:

* Country
* State
* City
* Department

---

# Access Selected Value

```csharp
ddlCountry.SelectedValue
```

or

```csharp
ddlCountry.SelectedItem.Text
```

---

# 9. Panel Control

A Panel acts like a container.

It can hold:

* Labels
* TextBoxes
* Buttons
* Images

Example:

```aspx
<asp:Panel
    ID="pnlUser"
    runat="server">
</asp:Panel>
```

Think of it as:

```text
A Box

Inside:
Label
TextBox
Button
```

---

# Dynamic Controls

Normally controls are created during design time.

Dynamic controls are created while the application is running.

Example:

User selects:

```text
5
```

from DropDownList.

System creates:

```text
Label1 TextBox1

Label2 TextBox2

Label3 TextBox3

Label4 TextBox4

Label5 TextBox5
```

automatically.

---

# Dynamic Control Flow

```text
Select Value
      ↓
Read Selected Value
      ↓
Loop
      ↓
Create Controls
      ↓
Add Controls To Panel
```

---

# 10. CheckBoxList Control

Used when multiple selections are allowed.

Example:

```aspx
<asp:CheckBoxList
    ID="cblCountry"
    runat="server">
</asp:CheckBoxList>
```

Output:

```text
☐ India

☐ USA

☐ Canada
```

User can select:

```text
☑ India

☑ Canada
```

---

# Adding Data into CheckBoxList

Think:

Country Name:

```text
India
```

Country Code:

```text
+91
```

After clicking Add:

```text
☐ India (+91)
```

gets added into CheckBoxList.

---

# Reading Selected Items

Think:

```text
☑ India

☑ Canada
```

When Display button is clicked:

```text
India

Canada
```

should be shown.

---

# Mapping Concepts to Lab Questions

| Question          | Concept                                            |
| ----------------- | -------------------------------------------------- |
| Calculator        | TextBox, Button, Event Handling                    |
| Registration Form | Label, TextBox, Button, HyperLink, Image, Calendar |
| Dynamic Panel     | Panel, DropDownList, Dynamic Controls              |
| Country Form      | TextBox, Button, CheckBoxList                      |

---

# Lab Questions

## Q1 Calculator

Operations:

* Addition
* Subtraction
* Multiplication
* Division
* Modulo

Think:

* How many TextBoxes are required?
* How will user choose operation?
* Where will result be displayed?

---

## Q2 Registration Form

Use:

* Label
* TextBox
* Button
* HyperLink
* Image
* LinkButton
* Calendar

Think:

What fields are required in a registration form?

---

## Q3 Dynamic Panel

Think:

User selects:

```text
3
```

How can 3 Labels and 3 TextBoxes be generated automatically?

---

## Q4 Country Name and Country Code

Think:

Step 1:

User enters:

```text
India
+91
```

Step 2:

Click Add

Step 3:

Store inside CheckBoxList

Step 4:

User selects items

Step 5:

Click Display

Step 6:

Show selected countries

---
