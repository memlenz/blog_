---
date: '2025-02-27T02:30:39+01:00'  
draft: false  
author: "Ayédoun Châ-Fine ADEBI"  
description: "Understand mathematical operations and manipulate strings in Python."  
title: "Operations and Expressions in Python"  
tags: ["python", "operations", "arithmetic", "strings"]  
categories: ["Python Course"]
series_order: 2
---

### **3. Operations and Expressions**  

In Python, you can perform various operations, whether on numbers, strings, or data collections. This section covers:  
✅ **Arithmetic operations**  
✅ **String operations**  
✅ **Some useful functions to manipulate values**  

---

## **1. Arithmetic Operations**  

Python works like a **calculator** and allows you to perform basic operations:  

| Operator | Description | Example | Result |
|----------|------------|---------|--------|
| `+` | Addition | `5 + 3` | `8` |
| `-` | Subtraction | `10 - 4` | `6` |
| `*` | Multiplication | `7 * 6` | `42` |
| `/` | Floating-point division | `20 / 5` | `4.0` |
| `//` | Integer division | `20 // 3` | `6` |
| `%` | Modulo (remainder) | `10 % 3` | `1` |
| `**` | Exponentiation (power) | `2 ** 3` | `8` |

#### **📌 Python Examples**  
```python
a = 10
b = 3

print("Addition:", a + b)  # 13
print("Subtraction:", a - b)  # 7
print("Multiplication:", a * b)  # 30
print("Division:", a / b)  # 3.3333...
print("Integer Division:", a // b)  # 3
print("Modulo:", a % b)  # 1
print("Power:", a ** b)  # 1000 (10^3)
```

---

## **2. String Operations**  

**Strings** (`str`) are widely used in programming. Python provides several **useful operations**:  

### **1️⃣ Concatenation**  
You can **combine** strings using `+`:  
```python
name = "Alice"
greeting = "Hello, " + name + "!"
print(greeting)  # Hello, Alice!
```

### **2️⃣ Repetition**  
You can **repeat** a string multiple times with `*`:  
```python
laugh = "Ha! " * 3
print(laugh)  # Ha! Ha! Ha!
```

### **3️⃣ Accessing Characters**  
Strings work like **arrays** of characters:  
```python
word = "Python"
print(word[0])  # P
print(word[-1])  # n (last character)
```

### **4️⃣ String Length**  
Using `len()`:  
```python
phrase = "Hello"
print(len(phrase))  # 5
```

### **5️⃣ Useful String Methods**  
| Method | Description | Example | Result |
|--------|------------|---------|--------|
| `upper()` | Converts to uppercase | `"hello".upper()` | `"HELLO"` |
| `lower()` | Converts to lowercase | `"HELLO".lower()` | `"hello"` |
| `strip()` | Removes spaces | `"  test  ".strip()` | `"test"` |
| `replace(a, b)` | Replaces `a` with `b` | `"Python".replace("Py", "C")` | `"Cthon"` |
| `split(sep)` | Splits a string into a list | `"a,b,c".split(",")` | `["a", "b", "c"]` |

#### **📌 Example Usage**  
```python
text = "  Python is awesome!  "
print(text.strip())  # Removes surrounding spaces
print(text.replace("Python", "Django"))  # Replaces a word
print(text.upper())  # Converts everything to uppercase
```

---

## **3. Some Useful Functions**  

### **🔹 The `round()` Function (Rounding a Number)**  
```python
number = 5.6789
print(round(number, 2))  # 5.68 (rounded to 2 decimals)
```

### **🔹 Calculating the Average of a List of Numbers**  
```python
grades = [10, 15, 20]
average = sum(grades) / len(grades)
print("Average:", average)  # 15.0
```

---

### **📌 Summary**  
✔️ Python allows you to perform **simple and advanced calculations**  
✔️ **Strings** offer various useful manipulations (`+`, `upper()`, `split()`, etc.)  
✔️ `round()` and `sum()` are useful functions for handling numbers  

💡 **Ready for the next step?** Next, we’ll cover **control structures** (conditions and loops) 🚀