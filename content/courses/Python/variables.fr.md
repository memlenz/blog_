---
date: '2025-02-26T02:26:44+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: 'Variables et commentaires en python'
description: "Apprenez les variables et commentaires en python"
tags: ["python", "variables"]
categories: ["Cours Python"]

---


Dans le monde de la programmation, les variables sont des outils essentiels pour stocker et manipuler des données. En Python, elles sont particulièrement flexibles et faciles à utiliser, ce qui les rend idéales pour les développeurs débutants tout en étant assez puissantes pour les utilisateurs avancés. Dans cet article, on va faire un tour d’horizon des variables en Python, en démystifiant leur fonctionnement et leur utilité à travers des exemples pratiques.

### Qu'est-ce qu'une variable ?

Une variable, c'est comme une boîte dans laquelle tu peux ranger des données. Ce qui est cool avec Python, c'est que tu n’as pas besoin de dire à l’avance quel type de données tu vas stocker dans cette boîte : Python va automatiquement déterminer le type de données selon ce que tu y mets. Si tu mets un nombre, la boîte devient un entier ; si tu y mets du texte, la boîte devient une chaîne de caractères, et ainsi de suite.

### Déclaration d'une variable

Déclarer une variable en Python est d'une simplicité enfantine. Il te suffit d’utiliser l’opérateur d’affectation (`=`) pour assigner une valeur à une variable. Voici un exemple simple :

```python
x = 10
nom = "Alice"
```

Dans cet exemple, `x` est une variable qui contient l’entier `10`, et `nom` est une variable qui contient la chaîne de caractères `"Alice"`.

### Les Types de Variables en Python

Python, étant un langage dynamique, gère différents types de données comme :

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


Python est assez intelligent pour déterminer le type d'une variable en fonction de la valeur que tu lui donnes. Cela rend l’écriture de code très fluide et rapide.

### Redéfinir des Variables

Tu peux changer la valeur d’une variable à tout moment. Ce qu’il faut retenir, c’est que la variable n’est pas liée à une valeur spécifique ; c’est comme si tu changeais le contenu de la boîte à volonté :

```python
x = 10
x = 20  # Maintenant x vaut 20
```

### Noms de Variables

Les noms de variables doivent suivre quelques règles simples :
- Un nom de variable ne peut pas commencer par un chiffre.
- Il peut contenir des lettres, des chiffres et des underscores (`_`).
- Python est sensible à la casse, donc `maVariable` et `mavariable` seront deux variables distinctes.

Il est recommandé de choisir des noms de variables clairs et explicites pour rendre ton code plus lisible. Par exemple, au lieu d’utiliser des noms comme `x` ou `temp`, opte pour quelque chose de plus parlant comme `age`, `prix_total`, ou `nombre_utilisateurs`.

### Variables et Types Mutables

Certaines variables en Python sont **mutables**, ce qui signifie que leur contenu peut être modifié après leur création. C’est le cas des listes, dictionnaires, et autres types comme les ensembles (`set`).

Exemple avec une liste :

```python
ma_liste = [1, 2, 3]
ma_liste[0] = 99  # On change le premier élément
print(ma_liste)  # Résultat : [99, 2, 3]
```

D’autres types, comme les entiers ou les chaînes de caractères, sont **immuables**, ce qui signifie qu’une fois qu’ils sont créés, tu ne peux pas modifier directement leur contenu. Par exemple :

```python
mon_texte = "Bonjour"
mon_texte[0] = "b"  # Cela va provoquer une erreur
```

### Variables Globales et Locales

Les variables en Python peuvent être **globales** ou **locales** :

- **Variables locales** : Elles sont définies à l’intérieur d’une fonction et n’existent que pendant l’exécution de cette fonction.
- **Variables globales** : Elles sont définies à l’extérieur de toute fonction et sont accessibles depuis n'importe où dans ton programme.

Exemple avec une variable locale :

```python
def ma_fonction():
    x = 5  # x est local à ma_fonction
    print(x)

ma_fonction()
print(x)  # Cela provoque une erreur car x n'est pas défini ici
```

### La Magie des Variables : L'Assignation Multiple

Python te permet d'assigner plusieurs variables en une seule ligne, ce qui peut rendre ton code plus compact :

```python
a, b, c = 1, 2, 3
print(a, b, c)  # Résultat : 1 2 3
```

C’est simple, mais très puissant, surtout quand tu veux manipuler plusieurs variables en même temps.

### Affichage et Commentaires  

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

### Conclusion

Les variables en Python, avec leur simplicité et flexibilité, sont des outils puissants qui te permettent de stocker et manipuler des données avec une grande facilité. En comprenant bien leur fonctionnement, tu pourras écrire un code plus lisible, plus efficace, et surtout, plus fun à coder.

Alors, à toi de jouer !
