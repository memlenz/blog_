---
date: '2025-03-03T05:57:31+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: 'La portee en Python'
description: "Comprendre et maîtriser la portée en Python"
tags: ["Python", "Portée"]
categories: ["Cours Python"]
series: ["Apprendre Python"]
series_order: 21
---


Si t’as déjà eu un bug chelou où une variable semble disparaître ou changer toute seule, bienvenue dans le monde de la **portée** (scope) en Python. C’est un concept simple mais fondamental : il définit où une variable est accessible dans ton code. Et si tu veux éviter des surprises, mieux vaut le maîtriser.  

---

## **Les différents types de portée en Python**  

Python a une structure bien définie pour gérer les variables. On parle souvent de **LEGB** (Local, Enclosing, Global, Built-in), un acronyme qui résume l’ordre de recherche des variables.  

### **1. Portée locale (Local Scope)**  
Une variable définie à l’intérieur d’une fonction est **locale** :  

```python
def ma_fonction():
    x = 10  # x est locale à cette fonction
    print(x)

ma_fonction()
print(x)  # Erreur : x n'existe pas ici
```
Ici, `x` est créée et utilisée **uniquement** dans `ma_fonction()`. Dès que la fonction termine, bye-bye `x` !  

### **2. Portée englobante (Enclosing Scope)**  
Quand une fonction est imbriquée dans une autre, elle peut voir les variables de la fonction englobante :  

```python
def externe():
    y = 20  # portée englobante

    def interne():
        print(y)  # y est visible ici !
    
    interne()

externe()
```
Là, `interne()` a accès à `y`, car Python regarde d’abord dans son propre scope, puis dans celui de `externe()`.  

### **3. Portée globale (Global Scope)**  
Une variable définie hors de toute fonction est **globale** :  

```python
z = 30  # variable globale

def afficher():
    print(z)  # Accessible partout

afficher()
print(z)  # Toujours accessible
```
Mais attention, si tu veux **modifier** une variable globale à l’intérieur d’une fonction, il faut le préciser :  

```python
a = 40

def changer_a():
    global a  # On dit à Python de modifier la variable globale
    a = 50

changer_a()
print(a)  # 50
```
Sans `global`, Python créerait une nouvelle variable locale `a` au lieu de modifier la globale.  

### **4. Portée built-in (Built-in Scope)**  
Ce sont les fonctions et variables intégrées à Python, genre `len()`, `print()`, etc.  

```python
print(len("Hello"))  # len() est dans la portée built-in
```

---

## **Quand ça devient bizarre : Les variables non locales**  

Quand une fonction imbriquée veut **modifier** une variable englobante (mais pas globale), on utilise `nonlocal` :  

```python
def externe():
    b = 60  # Variable englobante

    def interne():
        nonlocal b  # Permet de modifier b au lieu de créer une variable locale
        b = 70
    
    interne()
    print(b)  # 70

externe()
```
Sans `nonlocal`, `b` dans `interne()` serait une nouvelle variable locale et n’affecterait pas `b` de `externe()`.

---

## **Conclusion : Un jeu de pistes bien organisé**  

Python suit toujours cet ordre **LEGB** pour chercher une variable :  
1. **Local** : D’abord dans la fonction actuelle  
2. **Enclosing** : Puis dans les fonctions englobantes  
3. **Global** : Ensuite dans le script principal  
4. **Built-in** : Enfin dans les fonctions natives de Python  

Si tu comprends bien ça, tu éviteras des bugs étranges et tu gagneras en clarté dans ton code.  

🚀 **Prochain défi ?** Essaye de deviner la sortie du code suivant :  

```python
x = 100

def exo():
    x = 200
    def sub_exo():
        global x
        x = 300
    sub_exo()
    print(x)

exo()
print(x)
```

Réponse ? Teste et analyse pourquoi c’est ce résultat 😉
