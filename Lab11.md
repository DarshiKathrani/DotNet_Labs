# Lab 11 - Master Page and Nested Master Page

## Objective

Learn:

* Master Page
* ContentPlaceHolder
* Child Page
* Nested Master Page

---

# Why Do We Need Master Pages?

Suppose we have a College Website.

Pages:

* Home
* About
* Contact
* Student
* Faculty

Each page contains:

* Logo
* Menu
* Footer

Without Master Page:

```text
Home.aspx
  Logo
  Menu
  Footer

About.aspx
  Logo
  Menu
  Footer

Contact.aspx
  Logo
  Menu
  Footer
```

Problem:

* Duplicate code
* Difficult maintenance

---

# Solution : Master Page

Create common layout once.

```text
Master Page

Header

Menu

Content Area

Footer
```

All pages share the same layout.

---

# Structure of Master Page

```text
--------------------------------

HEADER

MENU

[ CONTENT ]

FOOTER

--------------------------------
```

---

# ContentPlaceHolder

Most Important Control.

Syntax:

```aspx
<asp:ContentPlaceHolder
ID="MainContent"
runat="server">
</asp:ContentPlaceHolder>
```

Purpose:

```text
Reserved Area

Child Page Content
Will Be Displayed Here
```

---

# Flow

```text
Master Page

      ↓

ContentPlaceHolder

      ↓

Child Page Content
```

---

# Creating Master Page

Steps:

1. Right Click Project
2. Add New Item
3. Select Master Page
4. Name: Site.master

---

# Child Page

A child page uses the layout of the Master Page.

Steps:

1. Add New Item
2. Web Form Using Master Page
3. Select Site.master

---

# Child Page Syntax

```aspx
<asp:Content
ContentPlaceHolderID="MainContent"
runat="server">

Welcome Students

</asp:Content>
```

---

# Visual Example

Master Page:

```text
Header

Menu

[ Content Area ]

Footer
```

Home.aspx:

```text
Welcome Students
```

Output:

```text
Header

Menu

Welcome Students

Footer
```

---

# Nested Master Page

Question:

What if Student Pages need their own menu?

Main Website Menu:

```text
Home
About
Contact
```

Student Menu:

```text
Profile
Attendance
Result
Fees
```

---

# Solution

Nested Master Page

```text
Main Master

      ↓

Student Master

      ↓

Profile.aspx

Result.aspx

Attendance.aspx
```

---

# Visual Structure

```text
Main Master

Logo
Main Menu

      ↓

Student Master

Student Menu

      ↓

Student Pages
```

---

# Difference

| Master Page       | Nested Master Page   |
| ----------------- | -------------------- |
| One Common Layout | Layout inside Layout |
| Simple Websites   | Large Websites       |
| Single Menu       | Multiple Menus       |

---

# Lab Questions

## Student Entity

Possible Pages:

* Home.aspx
* Student.aspx
* Contact.aspx

Common:

* Header
* Menu
* Footer

Use Master Page.

---

## Student Entity using Nested Master

Structure:

```text
Main Master

      ↓

Student Master

      ↓

Profile.aspx

Attendance.aspx

Result.aspx
```

---

# Quick Revision

Master Page:

```text
Common Layout
```

ContentPlaceHolder:

```text
Area For Child Content
```

Child Page:

```text
Uses Master Layout
```

Nested Master Page:

```text
Master Page Inside Another Master Page
```
