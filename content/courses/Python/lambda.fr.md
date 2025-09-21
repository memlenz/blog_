---
date: '2025-02-27T19:57:54+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: 'Les fonctions lambda en Python'
description: "Manipuler les fonctions lambda en Python"
tags: ["Python", "Lambda"]
categories: ["Cours Python"]
series: ["Apprendre Python"]
series_order: 16
---

**Les Fonctions Lambda en Python : Des Fonctions Ultra-Compactes**

Si tu es déjà familiarisé avec les fonctions classiques en Python, tu sais qu'elles peuvent parfois être un peu longues à écrire pour des tâches simples. C’est là que **les fonctions lambda** entrent en scène pour te simplifier la vie. Elles te permettent de créer des fonctions anonymes, en une seule ligne, super efficaces et parfaites pour les cas où tu n’as pas besoin de nommer ta fonction.

Dans cet article, on va explorer ce concept et comprendre comment tirer parti des **lambda** pour rendre ton code plus fluide, plus concis et plus puissant. Prêt à plonger dans ce monde compact et stylé ? Allons-y.

### 1. **C’est Quoi, Une Fonction Lambda ?**

Une fonction lambda, c'est une fonction **anonyme** et **inline** (sur une seule ligne) qui peut être utilisée partout où une fonction normale est attendue. Elle est idéale quand tu n’as besoin de la fonction que pour un petit calcul ou une opération rapide, et pas pour des traitements complexes.

Voici la syntaxe de base d’une fonction lambda :

```python
lambda arguments: expression
```

- **arguments** : Ce sont les entrées de la fonction, comme dans une fonction classique.
- **expression** : C’est ce que la fonction retourne, sans avoir besoin de `return`.

Exemple de fonction lambda simple :

```python
carre = lambda x: x ** 2
print(carre(5))  # 25
```

C’est aussi simple que ça ! Une fonction lambda qui prend un argument `x` et retourne `x**2`.

### 2. **Quand Utiliser Les Lambda ?**

Les lambdas sont parfaites dans les cas où tu veux **passer une fonction simple comme argument** dans une autre fonction, sans la définir ailleurs dans ton code. Elles sont souvent utilisées avec des fonctions comme `map()`, `filter()`, ou `sorted()`.

Voici quelques exemples classiques d’utilisation des lambdas.

### 3. **Avec `map()` : Transformer Une Liste en Une Seule Ligne**

La fonction `map()` applique une fonction à chaque élément d’un iterable (comme une liste) et renvoie un objet map. Et là, les lambdas brillent vraiment, car elles te permettent de créer des fonctions sans t’embêter à les définir séparément.

Exemple :

```python
nombres = [1, 2, 3, 4, 5]
carres = map(lambda x: x ** 2, nombres)
print(list(carres))  # [1, 4, 9, 16, 25]
```

Ici, la fonction lambda transforme chaque élément de la liste `nombres` en son carré.

### 4. **Avec `filter()` : Filtrer les Éléments en Une Ligne**

Si tu veux filtrer une liste en fonction d'une condition, `filter()` est ta fonction. Et les lambdas te permettent de le faire en un clin d’œil, sans une fonction définie à part.

Exemple :

```python
nombres = [1, 2, 3, 4, 5, 6]
pairs = filter(lambda x: x % 2 == 0, nombres)
print(list(pairs))  # [2, 4, 6]
```

Là, la lambda filtre les nombres pairs dans la liste `nombres`.

### 5. **Avec `sorted()` : Trier Comme un Chef**

Tu peux également utiliser des lambdas pour trier des listes de manière personnalisée avec la fonction `sorted()`. Par exemple, si tu as une liste de tuples et que tu veux trier par un élément spécifique, c’est ultra-simple avec une lambda.

Exemple :

```python
eleves = [("Alice", 23), ("Bob", 17), ("Charlie", 20)]
eleves_tries = sorted(eleves, key=lambda x: x[1])
print(eleves_tries)  # [('Bob', 17), ('Charlie', 20), ('Alice', 23)]
```

Ici, la lambda trie les élèves par âge, qui est le second élément de chaque tuple.

### 6. **Les Avantages des Lambdas**

- **Compactes et Concises** : Pas besoin de définir des fonctions longues quand une simple ligne suffit.
- **Flexibles** : Idéales pour des opérations rapides et des traitements courts.
- **Faciles à utiliser** : Parfaites pour être utilisées avec des fonctions comme `map()`, `filter()`, ou `sorted()`.

### 7. **Les Limites des Lambdas**

Les lambdas sont puissantes, mais elles ont aussi leurs limites. Elles sont **uniquement pour des expressions simples**. Si tu as besoin de faire des calculs complexes, des boucles, ou des conditions multiples, il vaut mieux opter pour une fonction classique. Une lambda ne doit jamais être un substitut à une fonction trop compliquée.

Exemple d’une mauvaise utilisation d’une lambda :

```python
# Trop complexe pour une lambda
complexe = lambda x: x**2 if x > 0 else -x + 2 * x ** 3
```

Pour ce genre de calculs, mieux vaut définir une fonction propre et claire.

### 8. **Fonction Lambda Multiple : Des Arguments à Gogo**

Les lambdas peuvent aussi prendre plusieurs arguments. La syntaxe est simple, tu les sépares par des virgules.

Exemple avec plusieurs arguments :

```python
addition = lambda x, y: x + y
print(addition(3, 5))  # 8
```

### Conclusion

Les fonctions lambda en Python sont un **outil super pratique** pour écrire du code compact, élégant et fonctionnel. Elles te permettent de réaliser des opérations simples et rapides sans encombrer ton code avec des définitions de fonctions classiques. À condition de les utiliser dans des situations adaptées, elles peuvent rendre ton code beaucoup plus lisible et agréable à manipuler.

Alors, prêt à faire de la magie avec les lambdas et à réduire la taille de ton code ?
