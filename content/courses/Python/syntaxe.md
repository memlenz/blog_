---
date: '2025-02-26T02:27:44+01:00'  
draft: false  
author: "Ayédoun Châ-Fine ADEBI"  
description: "Learn Python syntax, variables, and comments."  
title: "Syntax and Basics of Python Language"  
date: 2025-02-27  
tags: ["python", "syntax", "variables"]  
categories: ["Python Course"]
series_order: 1
---

### **2. Syntax and Basics of the Language**  

Python stands out for its simple and readable syntax. In this section, we will cover the fundamentals of writing Python code.  

---

### **1. Indentation: A Mandatory Rule**  
Unlike other languages that use curly braces `{}` or keywords (`begin` / `end`), Python uses **indentation** to structure code.  

#### ❌ Bad Example (Indentation Error)  
```python
if 5 > 2 :
print("Five is greater than 2")  # Error: Missing indentation!
```  

#### ✅ Correct Example  
```python
if 5 > 2:
    print("Five is greater than 2")  # Correct indentation
```  
📌 **Rule**: Indentation is usually **4 spaces** per level (avoid mixed tabs).  

---

### **2. Variables and Data Types**  
A variable is a **memory location** where a value is stored. Python is **dynamically typed**, meaning it automatically detects variable types.  

#### **📌 Declaration and Assignment**  
```python
name = "Alice"  # String
age = 25       # Integer
pi = 3.14      # Float
is_active = True  # Boolean
```

#### **📌 Main Data Types in Python**  
| Type | Example | Description |
|------|---------|------------|
| `str` (string) | `"Hello"` | Text |
| `int` (integer) | `42` | Whole number |
| `float` (floating point) | `3.14` | Decimal number |
| `bool` (boolean) | `True`, `False` | True or False |
| `list` (list) | `[1, 2, 3]` | Mutable collection |
| `tuple` (tuple) | `(1, 2, 3)` | Immutable collection |
| `dict` (dictionary) | `{"name": "Alice", "age": 25}` | Key-Value pair |
| `set` (set) | `{"apple", "banana"}` | Unique values set |

---

### **3. Output and Comments**  

#### **📌 The `print()` Function**  
It allows displaying text or variables on the screen.  
```python
print("Hello, world!")
name = "Alice"
print("Hello", name)
```
👉 Output:  
```
Hello, world!
Hello Alice
```

#### **📌 Comments**  
Comments help explain the code without being executed.  

✅ **Single-line comment**  
```python
# This is a comment
print("Hello")  # Displaying a message
```  

✅ **Multi-line comment**  
```python
"""
This is a comment
spanning multiple lines.
"""
print("Python is awesome!")
```

---

📌 **Summary**:  
✔️ Python uses **indentation** to structure code.  
✔️ **Variables** are dynamic and can store different data types.  
✔️ The `print()` function allows displaying text.  
✔️ **Comments** help document code.  

💡 Ready for the next step? Let's dive into **operations and expressions** in section 3! 🚀