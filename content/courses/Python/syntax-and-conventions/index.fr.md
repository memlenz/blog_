---
date: '2025-02-15T15:02:02+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: '🐍 Python : Syntaxe et Conventions de Base'
description: "Apprends les bases de la syntaxe et des conventions du langage pyhton"
tags:
  - Cours
  - Syntaxe
  - Conventions
  - Langages de Programmation
categories:
  - Python
  - Programmation
---

## 🔥 Introduction  

Bienvenue dans ce guide où on va poser les bases de Python. Oublie les cours trop théoriques, ici, on va **pratiquer** pour bien comprendre !  

On va commencer par :  
✅ Installer Python et préparer l’environnement  
✅ Découvrir la **syntaxe de base**  
✅ Comprendre comment **afficher du texte et des nombres**  
✅ Explorer les **types de données** (`int`, `float`, `bool`, `str`)  

Allez, c'est parti ! 🚀  

---

## 1️⃣ Préparer l’environnement  

### 🔹 Installer un éditeur de code  

On va utiliser **Visual Studio Code (VS Code)**, un éditeur populaire et puissant.  

1. **Télécharge-le ici** 👉 [code.visualstudio.com](https://code.visualstudio.com/)  
2. **Installe-le** en suivant les instructions pour ton système (Windows, macOS, Linux).  
3. **Désactive toutes les extensions** pour un environnement propre :  
   - Ouvre VS Code  
   - Va dans le **menu Extensions** (`Ctrl + Shift + X` ou `Cmd + Shift + X` sur Mac)  
   - Désactive tout en cliquant sur chaque extension et en choisissant **"Désactiver"**  

---

### 🔹 Installer Python  

1. **Télécharge Python** sur [python.org](https://www.python.org/downloads/)  
2. **Installe-le** en suivant les instructions de ton OS :  
   - **Windows :** Active l’option **"Add Python to PATH"** avant d’installer  
   - **Linux :** Ouvre un terminal et tape :  
     ```bash
     sudo apt install python3  # Pour Debian/Ubuntu
     sudo dnf install python3  # Pour Fedora
     sudo pacman -S python     # Pour Arch
     ```
   - **macOS :** Tape dans le terminal :  
     ```bash
     brew install python
     ```

3. **Vérifie l’installation** en tapant cette commande dans le terminal (ou PowerShell sur Windows) :  

   ```bash
   python3 --version
   ```

   **Exemple de sortie :**  
   ```
   Python 3.11.2
   ```

---

## 2️⃣ Écrire son premier programme  

Ouvre **VS Code**, crée un **nouveau fichier** nommé `first.py` et écris ceci :  

```python
print("This is fun.")
print('Yay! Printing.')
print("I'd much rather you 'not'.")
print('I "said" do not touch this.')
```

✅ **Sauvegarde le fichier (`Ctrl + S`)**  
✅ **Exécute-le dans le terminal VS Code** en tapant :  

```bash
python3 first.py
```

**Résultat attendu :**  
```
This is fun.
Yay! Printing.
I'd much rather you 'not'.
I "said" do not touch this.
```

💡 **Remarque importante** :  
- Tout ce qui est affiché entre **guillemets simples `'` ou doubles `"`** est du **texte** (`str`).  
- `print()` est la commande qui permet d’afficher du texte à l’écran.  

---

## 3️⃣ Afficher des nombres en Python  

### 🔹 Différence entre texte et nombres  

Quand tu écris du texte, tu dois **mettre des guillemets** (`" "` ou `' '`).  
Mais pour **les nombres**, ce n’est **pas nécessaire**.  

```python
print("42")  # Texte (str)
print(42)    # Nombre entier (int)
```

**Différence :**  
```
42   (affiché comme texte)
42   (affiché comme nombre)
```

### 🔹 Types de nombres en Python  

1. **Les entiers (`int`)** : nombres sans décimales  
   ```python
   print(10)  # 10
   print(-5)  # -5
   ```
2. **Les décimaux (`float`)** : nombres avec des virgules (utiliser `.` au lieu de `,`)  
   ```python
   print(3.14)  # 3.14
   print(-0.5)  # -0.5
   ```
3. **Opérations mathématiques**  

   Python suit la règle **PEMDAS** (Parenthèses, Exposants, Multiplication, Division, Addition, Soustraction) :  
   ```python
   print(5 + 2)    # 7
   print(10 - 3)   # 7
   print(6 / 2)    # 3.0 (division retourne un float)
   print(2 ** 3)   # 8 (exponentiation, 2^3)
   print(10 % 3)   # 1 (modulo, reste de la division)
   ```

---

## 4️⃣ Le type `bool` (Vrai ou Faux)  

En Python, il y a un type spécial appelé **booléen (`bool`)**, qui ne peut avoir que **deux valeurs** :  

✅ `True` (vrai)  
✅ `False` (faux)  

```python
print(True)   # True
print(False)  # False
```

### 🔹 Comparaisons  

Les `bool` sont souvent utilisés avec des comparaisons :  

```python
print(5 > 3)   # True
print(10 == 10)  # True
print(7 < 4)   # False
```

**Explication :**  
- `5 > 3` (5 est plus grand que 3) → ✅ **True**  
- `10 == 10` (10 est égal à 10) → ✅ **True**  
- `7 < 4` (7 est plus petit que 4) → ❌ **False**  

---

## 5️⃣ Les variables en Python  

Une **variable** est comme une boîte qui stocke une valeur.  

```python
nom = "Alice"
age = 25
est_majeur = age >= 18  # True
```

On peut ensuite les utiliser dans `print()` :  

```python
print(nom)  # Alice
print("Âge :", age)  # Âge : 25
print("Est majeur ?", est_majeur)  # Est majeur ? True
```

💡 **Règles pour nommer les variables :**  
- Doit commencer par une **lettre** ou `_`, mais pas un chiffre  
- Pas d’espace (`mon age ❌`, utiliser `mon_age ✅`)  
- Sensible à la casse (`Nom` ≠ `nom`)  

---

## 🎯 Exercices  

Essaie ces commandes dans le terminal Python :  

1️⃣ Que fait ce code ?  

```python
print("10" + "5")
print(10 + 5)
```

2️⃣ Devine la sortie avant d’exécuter ceci :  

```python
print(5 > 2)
print(10 == "10")
print(True + 3)
```

---

## 🏁 Conclusion  

🔥 Maintenant, tu sais comment :  
✅ Installer et configurer Python  
✅ Afficher du texte et des nombres  
✅ Faire des opérations mathématiques  
✅ Utiliser les types `int`, `float`, `bool`  
✅ Définir des variables  

🎯 **Prochain chapitre** : Les structures de contrôle (conditions et boucles).  

🚀 Continue à pratiquer, c’est comme ça qu’on progresse ! 💪