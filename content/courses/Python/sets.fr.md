---
date: '2025-02-27T19:27:26+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: 'Les sets en Python'
description: "manipuler des collections uniquement unique avec les sets en Python"
tags: ["Python", "sets"]
categories: ["Cours Python"]
---

Tu cherches à stocker des éléments sans te prendre la tête avec des doublons ? Les **sets** en Python sont là pour ça. Ces collections sont super utiles lorsque tu veux garantir que chaque élément dans ta collection soit unique. En plus, ils offrent une vitesse de recherche et de suppression ultra rapide. Bref, si tu veux de la simplicité et de l'efficacité, les sets devraient rapidement devenir tes alliés dans ton code Python.

Dans cet article, on va explorer ensemble ce qu’est un set, comment le manipuler, et pourquoi tu devrais les intégrer à ton arsenal. Pas besoin de se casser la tête, c’est simple, puissant et rapide.

### 1. **Créer un Set : Un Panier Sans Doublons**

Un set est une collection d’éléments qui ne peut pas contenir de doublons. Ça signifie qu’aucun élément ne peut apparaître plus d’une fois. Pour créer un set en Python, rien de plus simple. Tu utilises des accolades `{}`.

Exemple de set :

```python
fruits = {"pomme", "banane", "cerise"}
print(fruits)  # {"pomme", "banane", "cerise"}
```

Tu peux aussi créer un set vide avec `set()` :

```python
set_vide = set()
print(set_vide)  # set()
```

### 2. **Les Set et les Doublons : Adieu les Dupes**

L’un des principaux avantages des sets est qu’ils éliminent automatiquement les doublons. Si tu essaies d’ajouter un élément déjà présent, Python s'en fiche et le set ne change pas.

Exemple :

```python
fruits = {"pomme", "banane", "cerise", "pomme"}
print(fruits)  # {"pomme", "banane", "cerise"} (pas de doublon)
```

Cela te permet d’être certain qu’un élément n’apparaît qu’une seule fois dans ton set, sans avoir à faire de vérifications manuelles.

### 3. **Accéder aux Éléments : Pas d'Index, Mais Toujours Accessible**

Contrairement aux listes et aux tuples, les sets ne sont **pas indexés**, ce qui veut dire que tu ne peux pas accéder directement à un élément via son indice. Si tu veux obtenir un élément spécifique, tu devras le chercher directement ou utiliser des boucles.

Exemple avec une boucle :

```python
fruits = {"pomme", "banane", "cerise"}

for fruit in fruits:
    print(fruit)
```

Si tu veux tester si un élément existe dans le set, tu peux utiliser l'opérateur `in` :

```python
print("pomme" in fruits)  # True
print("orange" in fruits) # False
```

### 4. **Ajouter et Supprimer des Éléments : Manipuler Facilement**

Ajouter un élément à un set se fait avec `.add()`, et supprimer un élément se fait avec `.remove()` ou `.discard()`. 

- **`.add(x)`** : Ajoute l’élément `x` au set.
- **`.remove(x)`** : Supprime l’élément `x`, mais lèvera une erreur si `x` n’est pas dans le set.
- **`.discard(x)`** : Supprime l’élément `x` mais ne lèvera pas d’erreur si `x` n’est pas dans le set.

Exemple :

```python
fruits = {"pomme", "banane", "cerise"}

# Ajouter un élément
fruits.add("orange")
print(fruits)  # {"pomme", "banane", "cerise", "orange"}

# Supprimer un élément
fruits.remove("banane")
print(fruits)  # {"pomme", "cerise", "orange"}

# Discard ne lève pas d'erreur si l'élément n'est pas présent
fruits.discard("kiwi")  # Pas d'erreur même si "kiwi" n'est pas dans le set
```

Si tu veux vider complètement un set, tu peux utiliser `.clear()` :

```python
fruits.clear()
print(fruits)  # set()
```

### 5. **Opérations sur les Sets : L'Art des Combinaisons**

Les sets en Python supportent plusieurs opérations intéressantes qui te permettent de les combiner, les filtrer ou même faire des calculs mathématiques. Voici quelques opérations utiles :

#### **Union (`|`)**

L’union permet de combiner deux sets sans doublons.

```python
fruits = {"pomme", "banane", "cerise"}
legumes = {"carotte", "brocoli", "pomme"}

union = fruits | legumes
print(union)  # {"pomme", "banane", "cerise", "carotte", "brocoli"}
```

#### **Intersection (`&`)**

L’intersection te permet de garder uniquement les éléments présents dans les deux sets.

```python
fruits = {"pomme", "banane", "cerise"}
legumes = {"carotte", "brocoli", "pomme"}

intersection = fruits & legumes
print(intersection)  # {"pomme"}
```

#### **Différence (`-`)**

La différence permet de récupérer les éléments du premier set qui ne sont pas dans le second.

```python
fruits = {"pomme", "banane", "cerise"}
legumes = {"carotte", "brocoli", "pomme"}

difference = fruits - legumes
print(difference)  # {"banane", "cerise"}
```

#### **Différence Symétrique (`^`)**

La différence symétrique te donne les éléments qui sont dans l’un ou l’autre, mais pas dans les deux.

```python
fruits = {"pomme", "banane", "cerise"}
legumes = {"carotte", "brocoli", "pomme"}

diff_sym = fruits ^ legumes
print(diff_sym)  # {"banane", "cerise", "carotte", "brocoli"}
```

### 6. **Les Sets et l’Efficacité**

Les sets sont non seulement super pratiques, mais aussi **très performants**. Les recherches, ajouts et suppressions sont **en moyenne O(1)**, ce qui signifie que peu importe la taille de ton set, ces opérations se font quasiment instantanément. Ça, c’est un vrai gain en termes de performance, surtout quand tu manipules de grandes quantités de données.

### 7. **Set Imbriqué : Attention à la Composition**

Un set ne peut pas contenir de **set imbriqué**, car les sets sont des types non-hashables. Mais tu peux y placer des tuples, car les tuples sont immuables et donc hashables.

Exemple :

```python
set_imbrique = {("a", 1), ("b", 2)}
print(set_imbrique)  # {("a", 1), ("b", 2)}
```

### Conclusion

Les sets en Python sont des collections puissantes et efficaces qui permettent de stocker des éléments sans doublons et de réaliser des opérations mathématiques rapidement. Si tu cherches à simplifier ton code et à manipuler des collections de manière élégante, les sets sont un choix incontournable. À la fois rapides, simples et flexibles, ils devraient devenir un de tes outils favoris.

Alors, la prochaine fois que tu te retrouves face à des données uniques à gérer, n’oublie pas les sets. C’est une solution optimale pour garder ton code à la fois clair et performant.
