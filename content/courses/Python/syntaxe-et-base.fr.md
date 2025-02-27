---
date: '2025-02-26T02:27:44+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
description: "Apprenez la syntaxe de Python, les variables et les commentaires."
title: "Syntaxe et bases du langage Python"
date: 2025-02-27
tags: ["python", "syntaxe", "variables"]
categories: ["Cours Python"]
series_order: 1
---

### **2. Syntaxe et bases du langage**  

Python se distingue par une syntaxe simple et lisible. Dans cette section, nous allons voir les fondamentaux de l'écriture du code Python.  

---

### **1. L'Indentation : Une règle obligatoire**  
Contrairement à d'autres langages qui utilisent des accolades `{}` ou des mots-clés (`begin` / `end`), Python utilise **l'indentation** pour structurer le code.  

#### ❌ Mauvais exemple (erreur d'indentation)  
```python
if 5 > 2 :
print("Cinq est plus grand que 2")  # Erreur : manque d'indentation !
```  

#### ✅ Bon exemple  
```python
if 5 > 2:
    print("Cinq est plus grand que 2")  # Indentation correcte
```  
📌 **Règle** : L'indentation est généralement de **4 espaces** par niveau (évitez les tabulations mixtes).  

---

### **2. Les Variables et Types de Données**  
Une variable est une **zone de mémoire** où l’on stocke une valeur. Python est **dynamique**, ce qui signifie qu'il détecte automatiquement le type des variables.  

#### **📌 Déclaration et affectation**  
```python
nom = "Alice"  # Chaîne de caractères
age = 25       # Entier
pi = 3.14      # Flottant
est_actif = True  # Booléen
```

#### **📌 Les principaux types en Python**  
| Type | Exemple | Description |
|------|---------|------------|
| `str` (chaîne) | `"Hello"` | Texte |
| `int` (entier) | `42` | Nombre entier |
| `float` (flottant) | `3.14` | Nombre décimal |
| `bool` (booléen) | `True`, `False` | Vrai ou faux |
| `list` (liste) | `[1, 2, 3]` | Collection modifiable |
| `tuple` (tuple) | `(1, 2, 3)` | Collection non modifiable |
| `dict` (dictionnaire) | `{"nom": "Alice", "age": 25}` | Clé-Valeur |
| `set` (ensemble) | `{"pomme", "banane"}` | Ensemble unique |

---

### **3. Affichage et Commentaires**  

#### **📌 La fonction `print()`**  
Elle permet d'afficher du texte ou des variables à l'écran.  
```python
print("Bonjour, monde !")
nom = "Alice"
print("Bonjour", nom)
```
👉 Résultat :  
```
Bonjour, monde !
Bonjour Alice
```

#### **📌 Les commentaires**  
Les commentaires permettent d’expliquer le code sans l’exécuter.  

✅ **Commentaire sur une ligne**  
```python
# Ceci est un commentaire
print("Hello")  # Affichage d'un message
```  

✅ **Commentaire sur plusieurs lignes**  
```python
"""
Ceci est un commentaire
sur plusieurs lignes.
"""
print("Python est génial !")
```

---

📌 **Résumé** :  
✔️ Python utilise **l'indentation** pour structurer le code.  
✔️ Les **variables** sont dynamiques et peuvent stocker divers types de données.  
✔️ La fonction `print()` permet d’afficher du texte.  
✔️ Les **commentaires** aident à documenter le code.  

💡 Prêt pour la suite ? Passons aux **opérations et expressions** dans la section 3 ! 🚀