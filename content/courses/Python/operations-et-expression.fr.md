---
date: '2025-02-27T02:30:39+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
description: "Comprenez les opérations mathématiques et manipulez les chaînes de caractères en Python."
title: "Opérations et expressions en Python"
tags: ["python", "opérations", "arithmétique", "chaînes"]
categories: ["Cours Python"]
series_order: 2
---

### **3. Opérations et Expressions**  

En Python, on peut effectuer différentes opérations, que ce soit sur les nombres, les chaînes de caractères ou les collections de données. Cette section couvre :  
✅ **Les opérations arithmétiques**  
✅ **Les opérations sur les chaînes de caractères**  
✅ **Quelques fonctions utiles pour manipuler les valeurs**  

---

## **1. Opérations arithmétiques**  

Python fonctionne comme une **calculatrice** et permet d’effectuer des opérations de base :  

| Opérateur | Description | Exemple | Résultat |
|-----------|------------|---------|----------|
| `+` | Addition | `5 + 3` | `8` |
| `-` | Soustraction | `10 - 4` | `6` |
| `*` | Multiplication | `7 * 6` | `42` |
| `/` | Division (flottante) | `20 / 5` | `4.0` |
| `//` | Division entière | `20 // 3` | `6` |
| `%` | Modulo (reste de la division) | `10 % 3` | `1` |
| `**` | Exponentiation (puissance) | `2 ** 3` | `8` |

#### **📌 Exemples en Python**  
```python
a = 10
b = 3

print("Addition :", a + b)  # 13
print("Soustraction :", a - b)  # 7
print("Multiplication :", a * b)  # 30
print("Division :", a / b)  # 3.3333...
print("Division entière :", a // b)  # 3
print("Reste de la division :", a % b)  # 1
print("Puissance :", a ** b)  # 1000 (10^3)
```

---

## **2. Opérations sur les chaînes de caractères (Strings)**  

Les **chaînes de caractères** (`str`) sont très utilisées en programmation. Python propose plusieurs **opérations utiles** :  

### **1️⃣ Concaténation**  
On peut **assembler** des chaînes en utilisant `+` :  
```python
nom = "Alice"
salutation = "Bonjour, " + nom + " !"
print(salutation)  # Bonjour, Alice !
```

### **2️⃣ Répétition**  
On peut **répéter** une chaîne plusieurs fois avec `*` :  
```python
rire = "Ha! " * 3
print(rire)  # Ha! Ha! Ha!
```

### **3️⃣ Accès aux caractères**  
Les chaînes fonctionnent comme des **tableaux** de caractères :  
```python
mot = "Python"
print(mot[0])  # P
print(mot[-1])  # n (dernier caractère)
```

### **4️⃣ Longueur d'une chaîne**  
Utilisation de `len()` :  
```python
phrase = "Bonjour"
print(len(phrase))  # 7
```

### **5️⃣ Méthodes utiles**  
| Méthode | Description | Exemple | Résultat |
|---------|------------|---------|----------|
| `upper()` | Convertit en majuscules | `"hello".upper()` | `"HELLO"` |
| `lower()` | Convertit en minuscules | `"HELLO".lower()` | `"hello"` |
| `strip()` | Supprime les espaces | `"  test  ".strip()` | `"test"` |
| `replace(a, b)` | Remplace `a` par `b` | `"Python".replace("Py", "C")` | `"Cthon"` |
| `split(sep)` | Coupe une chaîne en une liste | `"a,b,c".split(",")` | `["a", "b", "c"]` |

#### **📌 Exemple d'utilisation**  
```python
texte = "  Python est génial!  "
print(texte.strip())  # Supprime les espaces autour
print(texte.replace("Python", "Django"))  # Remplace un mot
print(texte.upper())  # Met tout en majuscules
```

---

## **3. Quelques fonctions utiles**  

### **🔹 La fonction `round()` (arrondi d’un nombre)**  
```python
nombre = 5.6789
print(round(nombre, 2))  # 5.68 (arrondi à 2 décimales)
```

### **🔹 Calculer la moyenne d’une liste de nombres**  
```python
notes = [10, 15, 20]
moyenne = sum(notes) / len(notes)
print("Moyenne :", moyenne)  # 15.0
```

---

### **📌 Récapitulatif**  
✔️ Python permet d’effectuer **des calculs simples et avancés**  
✔️ Les **chaînes de caractères** offrent plusieurs manipulations utiles (`+`, `upper()`, `split()`, etc.)  
✔️ `round()` et `sum()` sont des fonctions utiles pour manipuler les nombres  

💡 **Prêt pour la suite ?** On pourra attaquer **les structures de contrôle** dans la section suivante (conditions et boucles) 🚀