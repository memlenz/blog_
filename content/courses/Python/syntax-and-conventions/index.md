---
date: '2025-02-15T15:02:02+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: '🐍 Python: Syntax and Basic Conventions'
description: "Learn the basics of Python syntax and conventions"
tags:
  - Course
  - Syntax
  - Conventions
  - Programming Languages
categories:
  - Python
  - Programming
---

## 🔥 Introduction  

Welcome to this guide where we’ll lay the foundation of Python. Forget overly theoretical courses—here, we’re going to **practice** to understand properly!  

We’ll start with:  
✅ Installing Python and setting up the environment  
✅ Discovering the **basic syntax**  
✅ Understanding how to **display text and numbers**  
✅ Exploring **data types** (`int`, `float`, `bool`, `str`)  

Alright, let’s go! 🚀  

---

## 1️⃣ Setting Up the Environment  

### 🔹 Installing a Code Editor  

We’ll use **Visual Studio Code (VS Code)**, a popular and powerful editor.  

1. **Download it here** 👉 [code.visualstudio.com](https://code.visualstudio.com/)  
2. **Install it** by following the instructions for your system (Windows, macOS, Linux).  
3. **Disable all extensions** for a clean environment:  
   - Open VS Code  
   - Go to the **Extensions menu** (`Ctrl + Shift + X` or `Cmd + Shift + X` on Mac)  
   - Disable everything by clicking on each extension and choosing **"Disable"**  

---

### 🔹 Installing Python  

1. **Download Python** from [python.org](https://www.python.org/downloads/)  
2. **Install it** following your OS instructions:  
   - **Windows:** Enable the **"Add Python to PATH"** option before installing  
   - **Linux:** Open a terminal and type:  
     ```bash
     sudo apt install python3  # For Debian/Ubuntu
     sudo dnf install python3  # For Fedora
     sudo pacman -S python     # For Arch
     ```
   - **macOS:** Type in the terminal:  
     ```bash
     brew install python
     ```

3. **Verify the installation** by running this command in the terminal (or PowerShell on Windows):  

   ```bash
   python3 --version
   ```

   **Example output:**  
   ```
   Python 3.11.2
   ```

---

## 2️⃣ Writing Your First Program  

Open **VS Code**, create a **new file** named `first.py`, and write this:  

```python
print("This is fun.")
print('Yay! Printing.')
print("I'd much rather you 'not'.")
print('I "said" do not touch this.')
```

✅ **Save the file (`Ctrl + S`)**  
✅ **Run it in the VS Code terminal** by typing:  

```bash
python3 first.py
```

**Expected output:**  
```
This is fun.
Yay! Printing.
I'd much rather you 'not'.
I "said" do not touch this.
```

💡 **Important note:**  
- Anything between **single `'` or double `"` quotes** is **text** (`str`).  
- `print()` is the command used to display text on the screen.  

---

## 3️⃣ Displaying Numbers in Python  

### 🔹 Difference Between Text and Numbers  

When writing text, you must **use quotes** (`" "` or `' '`).  
For **numbers**, quotes are **not needed**.  

```python
print("42")  # Text (str)
print(42)    # Integer (int)
```

**Difference:**  
```
42   (displayed as text)
42   (displayed as a number)
```

### 🔹 Number Types in Python  

1. **Integers (`int`)**: Whole numbers  
   ```python
   print(10)  # 10
   print(-5)  # -5
   ```
2. **Decimals (`float`)**: Numbers with decimal points (`.` instead of `,`)  
   ```python
   print(3.14)  # 3.14
   print(-0.5)  # -0.5
   ```
3. **Math Operations**  

   Python follows the **PEMDAS** rule (Parentheses, Exponents, Multiplication, Division, Addition, Subtraction):  
   ```python
   print(5 + 2)    # 7
   print(10 - 3)   # 7
   print(6 / 2)    # 3.0 (division returns a float)
   print(2 ** 3)   # 8 (exponentiation, 2^3)
   print(10 % 3)   # 1 (modulo, remainder of division)
   ```

---

## 4️⃣ The `bool` Type (True or False)  

In Python, there is a special type called **boolean (`bool`)**, which can have **only two values**:  

✅ `True` (true)  
✅ `False` (false)  

```python
print(True)   # True
print(False)  # False
```

### 🔹 Comparisons  

Booleans are often used with comparisons:  

```python
print(5 > 3)   # True
print(10 == 10)  # True
print(7 < 4)   # False
```

**Explanation:**  
- `5 > 3` (5 is greater than 3) → ✅ **True**  
- `10 == 10` (10 is equal to 10) → ✅ **True**  
- `7 < 4` (7 is less than 4) → ❌ **False**  

---

## 5️⃣ Variables in Python  

A **variable** is like a box that stores a value.  

```python
name = "Alice"
age = 25
is_adult = age >= 18  # True
```

We can then use them in `print()`:  

```python
print(name)  # Alice
print("Age:", age)  # Age: 25
print("Is adult?", is_adult)  # Is adult? True
```

💡 **Rules for Naming Variables:**  
- Must start with a **letter** or `_`, but not a number  
- No spaces (`my age ❌`, use `my_age ✅`)  
- Case-sensitive (`Name` ≠ `name`)  

---

## 🎯 Exercises  

Try these commands in the Python terminal:  

1️⃣ What does this code do?  

```python
print("10" + "5")
print(10 + 5)
```

2️⃣ Guess the output before running this:  

```python
print(5 > 2)
print(10 == "10")
print(True + 3)
```

---

## 🏁 Conclusion  

🔥 Now, you know how to:  
✅ Install and set up Python  
✅ Display text and numbers  
✅ Perform mathematical operations  
✅ Use `int`, `float`, and `bool` types  
✅ Define variables  

🎯 **Next chapter**: Control structures (conditions and loops).  

🚀 Keep practicing—that’s how you improve! 💪