---
date: "2025-04-09T21:29:56+01:00"
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: "🎯 Implémentation d'un foramateur de texte en python"
description: "Découvrez comment manipuler des chaines de caractère en python pour créer des listes"
categories: ["Projets Python",]
tags: ["Python", "Algorithmie"]
---


# Mastering Text Manipulation with Python: Building a Bullet Point Formatter

In today's digital workplace, formatting text quickly and efficiently can save precious time. As a Python developer, I recently created a utility tool that demonstrates how a few lines of Python code can streamline everyday tasks. Let me walk you through my bullet point formatter script and highlight the Python skills it showcases.

## The Problem

We've all been there - copying text from various sources that needs reformatting before use. Perhaps you're extracting items from an email, document, or webpage and need to transform them into a clean, bulleted list. Doing this manually is tedious, especially with longer texts.

## The Solution: bulletPointAdder.py

My solution is a simple yet powerful Python script that takes text from your clipboard, formats each line with bullet points, and places the result back in your clipboard - ready to paste wherever you need it.

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-
"""
    Nom du fichier : bulletPointAdder.py
    Description : Formate du texte pour obtenir une liste à puce
    Auteur : ADEBI Châ-Fine Ayédoun achafine@gmail.com
    Date : 2025-04-08
"""
```

## Python Skills Demonstrated

### 1. Working with External Libraries

The script uses `pyperclip`, a third-party library that provides cross-platform clipboard functionality:

```python
import pyperclip
```

This demonstrates knowledge of Python's ecosystem and how to leverage existing libraries to extend functionality without reinventing the wheel.

### 2. Regular Expressions Mastery

One of the most powerful features of the script is its text processing capability using regular expressions:

```python
REGEX = r'^[\d\.\)\s\-_]+'  # Pattern to match various numbering formats
line = re.sub(REGEX, '', line)
```

This regex pattern identifies and removes different types of numbering or bullet formats that might already exist in the text. It handles numbered lists (like "1. Item"), parenthetical numbering (like "1) Item"), and various bullet styles.

### 3. Constants for Configuration

The script uses constants to make configuration changes easy and centralized:

```python
# Constantes
BULLET = '.'  # Vos nouvelles lignes peuvent commencer par: '•', '-', '*', '→'
REGEX = r'^[\d\.\)\s\-_]+'  # Vous pouvez changer le la logique des lignes
```

This approach follows the principle of separating configuration from logic, making the code more maintainable.

### 4. Function Decomposition and Clean Code Principles

The script is divided into clear, single-purpose functions:

```python
def paste_from_clipboard() -> str:
    """On récupère le contenu du clipboard"""
    
def bullet_point_adder() -> str:
    """On modifie chaque ligne pour en faire des listes à puces"""
    
def paste_to_clipboard() -> None:
    """On copie le contenu dans le clipboard"""
```

Each function has a clear responsibility, making the code easier to understand, test, and maintain.

### 5. Type Hints

The code uses Python's type hints to indicate function return types:

```python
def paste_from_clipboard() -> str:
```

This makes the code more self-documenting and allows for better tooling support and error detection.

### 6. String Manipulation and Formatting

The script demonstrates proficiency with string operations:

```python
line = f'{BULLET} {line}'  # f-strings for clean string formatting
return '\n'.join(formated_lines)  # Joining lists into strings
welcome.center(len(welcome) + 5, '*')  # String alignment and padding
```

These techniques show knowledge of Python's rich string manipulation capabilities.

### 7. List Comprehension and Iteration

While not using list comprehensions directly, the code effectively processes lists through iteration:

```python
formated_lines = []
for line in list_content:
    # Processing logic
    formated_lines.append(line)
```

### 8. Error Handling

The main execution block includes proper exception handling:

```python
try:
    # Main processing
except Exception as e:
    print(f"Erreur : {str(e)}")
```

This ensures the script gracefully handles potential errors rather than crashing.

### 9. Docstrings and Documentation

Every function includes proper docstrings explaining its purpose:

```python
def bullet_point_adder() -> str:
    """On modifie chaque ligne pour en faire des listes à puces"""
```

Additionally, the script header provides metadata about the author, purpose, and date.

### 10. Proper Program Structure

The script follows the Python convention of using the `if __name__ == "__main__":` guard to separate executable code from importable modules:

```python
if __name__ == "__main__":
    # Execution code here
```

This allows the script to be imported as a module without executing the main functionality.

## Real-World Application

This script may be simple, but it demonstrates how Python can be used to automate routine tasks. For example, if you're preparing a presentation and need to format a list of items, or if you're taking notes and want to quickly convert them to a bulleted format, this tool saves time and ensures consistency.

## Conclusion

Building small utility scripts like `bulletPointAdder.py` is an excellent way to sharpen your Python skills while creating tools that make your daily workflow more efficient. The script showcases a range of Python techniques from basic string manipulation to regular expressions, all wrapped in a clean, well-structured program.

What everyday tasks do you automate with Python? I'd love to hear about your utility scripts in the comments!

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-
"""
    Nom du fichier : bulletPointAdder.py
    Description : Formate du texte pour obtenir une liste à puce
    Auteur : ADEBI Châ-Fine Ayédoun achafine@gmail.com
    Date : 2025-04-08
"""


import re
import pyperclip


# Constantes
BULLET = '.'  # Vos nouvelles lignes peuvent commencer par: '•', '-', '*', '→'
REGEX = r'^[\d\.\)\s\-_]+'  # Vous pouvez changer le la logique des lignes


def paste_from_clipboard() -> str:
    """On récupère le contenu du clipboard"""
    return pyperclip.paste()


def bullet_point_adder() -> str:
    """On modifie chaque ligne pour en faire des listes à puces"""
    content = paste_from_clipboard().strip()
    # On convertis le contenu en liste
    list_content = content.split('\n')
    # Formatage des lignes
    formated_lines = []
    for line in list_content:
        line = line.strip()
        # Gestion des lignes vides
        if not line:
            formated_lines.append(line)
            continue
        # Gestion des lignes qui commencent par des chiffres
        line = re.sub(REGEX, '', line)
        # Ajout des puces
        if not line.startswith(BULLET):
            line = f'{BULLET} {line}'
        formated_lines.append(line)
    return '\n'.join(formated_lines)


def paste_to_clipboard() -> None:
    """On copie le contenu dans le clipboard"""
    pyperclip.copy(bullet_point_adder())


if __name__ == "__main__":
    welcome = "Welcome to the Bullet Point Adder"
    print(welcome.center(len(welcome) + 5, '*'))
    try:
        print("Processing".ljust(len(welcome)+5, '.'))
        paste_to_clipboard()
        print("successfully paste".center(len(welcome) + 5, '*'))
    except Exception as e:
        print(f"Erreur : {str(e)}")
```


📌 **Follow me for more Python and dev content!**  
👉 [[Dev.to](https://dev.to/memlenz) / [GitHub](https://github.com/memlenz) / [Twitter Profile](https://twitter.com/achafine)]
