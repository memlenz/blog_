---
date: '2025-02-27T19:47:35+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: 'Les boucles en Python'
description: "Maîtriser les boucles en python"
tags: ["Python", "for", "while"]
categories: ["Cours Python"]
---


**Les Structures de Boucles en Python : Reprends le Contrôle de ton Code**

Quand tu veux que ton programme répète une série d’actions plusieurs fois sans avoir à tout coder à la main, les boucles sont ton meilleur ami. En Python, elles sont simples à comprendre et te permettent de faire des actions répétitives de manière efficace et élégante.

Dans cet article, on va plonger dans les structures de boucles en Python, te montrer les différents types de boucles et comment les utiliser pour rendre ton code plus fluide. Si tu veux comprendre comment exécuter un bloc de code à plusieurs reprises de manière contrôlée, accroche-toi, on part explorer ça ensemble !

### 1. **La Boucle `for` : L'Art de Parcourir**

La boucle `for` en Python est probablement l'une des boucles les plus utilisées. Elle te permet de parcourir des éléments dans un itérable (comme une liste, une chaîne de caractères, ou un objet range). La syntaxe est simple et directe, c’est presque comme si tu déléguais le travail à Python.

Exemple :

```python
fruits = ["pomme", "banane", "cerise"]
for fruit in fruits:
    print(fruit)
```

Sortie :

```
pomme
banane
cerise
```

Ici, Python parcourt chaque élément de la liste `fruits` et exécute le bloc de code à l’intérieur de la boucle pour chaque élément. C’est un moyen super propre d’itérer sur une collection.

#### Avec `range()`

Si tu n’as pas de liste à parcourir, tu peux utiliser `range()` pour générer une séquence de nombres. Ça peut être utile pour des boucles où tu as besoin de répéter un certain nombre de fois un bloc de code, sans forcément avoir une collection d’éléments à itérer.

Exemple :

```python
for i in range(5):  # De 0 à 4
    print(i)
```

Sortie :

```
0
1
2
3
4
```

Tu peux aussi spécifier un début, une fin, et un pas :

```python
for i in range(1, 10, 2):  # De 1 à 9, avec un pas de 2
    print(i)
```

Sortie :

```
1
3
5
7
9
```

### 2. **La Boucle `while` : Tant Que…**

La boucle `while` en Python répète un bloc de code tant qu’une condition est vraie. C’est super utile quand tu ne sais pas exactement combien de fois tu dois répéter l’action, mais que tu sais qu’une condition doit rester valide.

Exemple simple :

```python
compteur = 0
while compteur < 5:
    print(compteur)
    compteur += 1
```

Sortie :

```
0
1
2
3
4
```

La condition `compteur < 5` reste vraie tant que le compteur est inférieur à 5, et à chaque itération, tu augmentes le compteur pour faire en sorte que la boucle s’arrête un jour.

**Attention aux Boucles Infinites !**

Si tu oublies de mettre à jour la condition dans la boucle `while`, tu risques de créer une boucle infinie qui va bloquer ton programme. C’est pas super fun, croyez-moi.

### 3. **La Boucle `for` avec des Conditions : Filtrer au Vol**

Il arrive que tu veuilles parcourir une liste, mais n’exécuter une action que sous certaines conditions. Grâce à des conditions à l’intérieur de ta boucle `for`, tu peux filtrer facilement les éléments qui t’intéressent.

Exemple :

```python
nombres = [1, 2, 3, 4, 5, 6, 7, 8, 9]
for nombre in nombres:
    if nombre % 2 == 0:  # Si le nombre est pair
        print(nombre)
```

Sortie :

```
2
4
6
8
```

Ici, la boucle passe à chaque élément de la liste, mais n'affiche que les nombres pairs.

### 4. **La Boucle `for` avec `else` : Le Bonus Après la Boucle**

Ce qui est un peu spécial avec Python, c’est que tu peux ajouter une clause `else` à une boucle `for` ou `while`. Ce `else` s’exécutera uniquement lorsque la boucle **ne sera pas terminée par un `break`**, c’est-à-dire qu’elle s’est exécutée entièrement.

Exemple :

```python
for i in range(5):
    print(i)
else:
    print("Fin de la boucle")
```

Sortie :

```
0
1
2
3
4
Fin de la boucle
```

Le bloc `else` ne s'exécute que si la boucle a parcouru tous les éléments sans être interrompue par un `break`. Si tu utilises un `break` pour sortir prématurément de la boucle, l'`else` sera ignoré.

### 5. **La déclaration `break` : L'Interruption Contrôlée**

La déclaration `break` permet de sortir immédiatement d’une boucle, qu’elle soit `for` ou `while`. C’est utile si tu veux arrêter l’exécution dès qu'une certaine condition est remplie.

Exemple :

```python
for i in range(10):
    if i == 5:
        print("Condition remplie, arrêt de la boucle.")
        break
    print(i)
```

Sortie :

```
0
1
2
3
4
Condition remplie, arrêt de la boucle.
```

Ici, dès que `i` atteint 5, la boucle s’arrête et le message est affiché. La boucle n’ira pas au-delà.

### 6. **La déclaration `continue` : Passer à l’Itération Suivante**

Si tu veux sauter une itération spécifique dans une boucle, tu peux utiliser `continue`. Cela permet de passer directement à l’itération suivante sans exécuter le reste du code pour cette itération.

Exemple :

```python
for i in range(5):
    if i == 2:
        continue  # Sauter l'itération quand i vaut 2
    print(i)
```

Sortie :

```
0
1
3
4
```

Dans cet exemple, lorsque `i` est égal à 2, l'itération est ignorée et on passe directement à 3.

### 7. **Les Boucles Imbriquées : Pour les Cas Complexes**

Il est tout à fait possible de mettre une boucle à l’intérieur d’une autre, ce qu’on appelle une **boucle imbriquée**. C’est utile, par exemple, quand tu travailles avec des listes de listes (ou des matrices).

Exemple :

```python
for i in range(3):
    for j in range(2):
        print(f"i={i}, j={j}")
```

Sortie :

```
i=0, j=0
i=0, j=1
i=1, j=0
i=1, j=1
i=2, j=0
i=2, j=1
```

### Conclusion

Les boucles en Python sont essentielles pour automatiser les répétitions de code. Que tu utilises `for` pour parcourir des collections ou `while` pour répéter une tâche tant qu’une condition est vraie, tu as toutes les armes pour gérer des actions répétitives avec élégance. Et avec des outils comme `break`, `continue` et `else`, tu as un contrôle total sur le flux d’exécution.

Maintenant, à toi de jouer : dans ton prochain projet, essaie de tirer parti des boucles pour rendre ton code plus lisible et puissant. Les boucles sont un élément clé du **"répétable"** dans la programmation, et maîtriser leur utilisation peut vraiment booster ton efficacité.
