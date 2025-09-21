---
date: '2025-02-27T12:30:01+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: 'Les nombres en Python'
description: "Manipulez les nombres en Python, de l'Intégrale à la décimale"
tags: ["Python", "Nombres"]
categories: ["Cours Python"]
series: ["Apprendre Python"]
series_order: 4
---

**Les Nombres en Python : De l'Intégrale à la Décimale**

Les nombres sont, sans surprise, l'une des pierres angulaires de la programmation. Et en Python, c'est un terrain de jeu assez large que tu vas découvrir. Que tu manipules des entiers pour compter des objets ou des flottants pour des calculs de précision, Python te fournit tout un arsenal pour travailler avec des chiffres de manière fluide et intuitive. Dans cet article, on plonge dans les différentes facettes des nombres en Python, avec des exemples concrets et quelques astuces qui te faciliteront la vie.

### 1. **Les Entiers (`int`) : La Base de Tout**

Les entiers, c’est la base. Ce sont des nombres sans virgule, que ce soit des nombres positifs, négatifs, ou nuls. En Python, tu n’as même pas à t'inquiéter de la taille maximale d’un entier. Python gère des entiers de tailles presque infinies, un vrai plus quand tu travailles avec de gros calculs.

```python
a = 100
b = -42
c = 0
```

Pas de souci ici. Python va gérer ça sans broncher. Et si tu as besoin d’un nombre particulièrement grand ou petit, tu n’as qu’à taper directement le nombre. Tu n’auras pas à te soucier des limites de stockage comme dans certains autres langages.

### 2. **Les Nombres à Virgule Flottante (`float`) : La Précision au Détail**

Les flottants, ce sont les nombres qui ont des décimales. Si tu veux effectuer des calculs qui nécessitent de la précision, comme en science ou en économie, tu feras forcément appel à eux. Python te permet de manipuler des flottants avec une simplicité déconcertante.

```python
pi = 3.14159
temperature = -5.67
```

Les flottants sont utiles pour des calculs comme des moyennes, des pourcentages, ou des calculs trigonométriques. Mais garde en tête qu’ils ne sont pas toujours parfaitement précis à cause de la manière dont ils sont représentés en mémoire. Si tu as besoin d'une précision de dingue, tu peux aussi utiliser le module `decimal` qui te permet de travailler avec des flottants à précision arbitraire.

### 3. **Les Opérations Mathématiques : Les Fondamentaux**

Que tu sois en train de coder une simple calculatrice ou de résoudre des équations complexes, Python te permet d'effectuer une large gamme d'opérations sur tes nombres. Voici les plus basiques :

- **Addition** : `+`
- **Soustraction** : `-`
- **Multiplication** : `*`
- **Division (flottante)** : `/`
- **Division entière** : `//`
- **Modulo (reste de la division)** : `%`
- **Exponentiation** : `**`

Voici un petit exemple pour voir comment ça marche :

```python
a = 10
b = 3

# Opérations
addition = a + b
soustraction = a - b
multiplication = a * b
division = a / b
division_entière = a // b
modulo = a % b
puissance = a ** b

print(f"Addition: {addition}, Soustraction: {soustraction}, Multiplication: {multiplication}")
print(f"Division: {division}, Division entière: {division_entière}, Modulo: {modulo}")
print(f"Puissance: {puissance}")
```

### 4. **Les Nombres Complexes (`complex`) : Quand les Réels ne Suffisent Pas**

Python permet aussi de travailler avec des **nombres complexes**, ce qui est parfait si tu touches à l'algèbre complexe ou à des calculs nécessitant une composante imaginaire.

Un nombre complexe se compose de deux parties : une réelle et une imaginaire. La syntaxe de base est la suivante :

```python
z = 3 + 4j  # 3 est la partie réelle et 4j la partie imaginaire
```

Tu peux effectuer des opérations sur ces nombres complexes comme sur des nombres réels. Python gère ça tout seul, et tu peux extraire la partie réelle et imaginaire avec les attributs `real` et `imag`.

```python
print(z.real)  # 3.0
print(z.imag)  # 4.0
```

### 5. **La Précision des Flottants : Les Pièges à Éviter**

Petite remarque importante. Les flottants, comme mentionné plus tôt, peuvent parfois entraîner des imprécisions en raison de la façon dont ils sont stockés en mémoire. Par exemple, si tu fais une opération simple comme :

```python
a = 0.1 + 0.2
print(a)
```

Tu pourrais t'attendre à voir `0.3`, mais Python pourrait afficher quelque chose comme `0.30000000000000004`. Pour éviter ces erreurs d’arrondi, tu peux utiliser des outils comme le module `decimal` ou arrondir les résultats avec la fonction `round()`.

```python
a = round(0.1 + 0.2, 2)
print(a)  # Affiche 0.3
```

### 6. **Conversion entre Types Numériques**

Parfois, tu voudras peut-être convertir des nombres d’un type à l’autre. Par exemple, passer d’un flottant à un entier, ou inversement. Python propose plusieurs fonctions de conversion intégrées :

- `int()` : Convertit en entier.
- `float()` : Convertit en flottant.

```python
x = 3.14
y = int(x)  # Convertit 3.14 en 3
z = float(5)  # Convertit 5 en 5.0

print(y, z)
```

### 7. **Les Fonctions Utiles pour les Nombres**

Python t’offre une boîte à outils pleine de fonctions pour manipuler les nombres, comme :

- `abs(x)` : Retourne la valeur absolue de `x`.
- `pow(x, y)` : Retourne `x` élevé à la puissance `y`.
- `min(x, y)` et `max(x, y)` : Retourne respectivement le plus petit et le plus grand des deux nombres.

### Conclusion

Les nombres sont l’un des éléments les plus simples, mais aussi les plus puissants en Python. Que tu travailles avec des entiers pour des indices de liste ou des flottants pour des calculs scientifiques, Python te fournit tout ce dont tu as besoin pour jongler avec les chiffres sans te prendre la tête. 

Maintenant que tu maîtrises les bases des nombres en Python, tu es prêt à t'attaquer à des projets plus ambitieux, que ce soit pour créer des applications, résoudre des problèmes mathématiques complexes ou même explorer l'algorithmique. Rappelle-toi que la pratique est la clé : expérimente, joue avec les nombres et tu deviendras rapidement plus à l'aise.
