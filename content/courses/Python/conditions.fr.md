---
date: '2025-02-27T19:39:29+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: 'Les structures conditionnelles avec Python'
description: "Prendre des décisions en Python grâce aux structures conditionnelles"
tags: ["Python", "Conditions", "if", "else", "elif"]
categories: ["Cours Python"]
---

Si la programmation était une histoire, les structures conditionnelles seraient les moments où l'intrigue prend un tournant. Tu sais, ces points où ton programme doit choisir quel chemin emprunter. **Les structures conditionnelles** te permettent de dire à ton code : "Si cette condition est vraie, fais ça, sinon fais autre chose." C’est un peu comme dans la vraie vie, où tu choisis une action en fonction de ce qui se passe autour de toi.

En Python, ces structures sont simples mais puissantes. Elles vont t'aider à écrire des programmes réactifs, capables de prendre des décisions intelligentes en fonction de données ou d'entrées utilisateur. Alors, on va plonger dans le **système décisionnel** de Python et t’apprendre à l'utiliser pour que ton code devienne encore plus dynamique.

### 1. **La Structure de Base : `if`**

La structure `if` est la base des décisions en Python. Elle permet de vérifier une condition et d'exécuter un bloc de code si cette condition est **vraie**. C’est comme dire "si cette condition se vérifie, alors fais ceci."

Exemple :

```python
age = 18

if age >= 18:
    print("Tu es majeur.")
```

Ici, si la condition `age >= 18` est vraie, le programme affiche "Tu es majeur." Sinon, il ne fait rien.

### 2. **Le `else` : Quand Ça Ne Passe Pas, Fais Ça**

Le `else` est ce qui se passe **quand la condition `if` n'est pas vraie**. C’est une alternative qui permet de dire : "Si la première condition n'est pas remplie, fais ça à la place."

Exemple :

```python
age = 16

if age >= 18:
    print("Tu es majeur.")
else:
    print("Tu es mineur.")
```

Si `age` est inférieur à 18, le programme affiche "Tu es mineur." Sinon, il afficherait "Tu es majeur."

### 3. **Le `elif` : Quand Tu As Plusieurs Choix**

Tu veux tester plusieurs conditions ? C’est là que le `elif` (qui signifie "else if") entre en jeu. Il permet d'ajouter des conditions supplémentaires si la première condition n'est pas remplie.

Exemple :

```python
age = 20

if age < 18:
    print("Tu es mineur.")
elif age >= 18 and age < 21:
    print("Tu es majeur, mais pas encore assez vieux pour boire de l'alcool.")
else:
    print("Tu es majeur et tu peux boire de l'alcool.")
```

Ici, si l’âge est entre 18 et 20 ans, le programme affiche un message spécifique pour cette tranche d’âge. Sinon, il affiche un autre message pour les plus de 21 ans.

### 4. **Les Conditions Complexes : Combiner les Tests**

Tu peux combiner plusieurs conditions pour créer des tests plus complexes en utilisant **`and`** et **`or`**. Ça te permet de prendre des décisions sur des critères multiples.

- **`and`** : La condition sera vraie seulement si **toutes les conditions** sont vraies.
- **`or`** : La condition sera vraie si **au moins une** des conditions est vraie.

Exemple avec `and` :

```python
age = 25
a_licence = True

if age >= 18 and a_licence:
    print("Tu peux conduire.")
else:
    print("Tu ne peux pas conduire.")
```

Ici, l’utilisateur doit avoir 18 ans ou plus **et** une licence pour pouvoir conduire.

Exemple avec `or` :

```python
a_licence = False
est_parent = True

if a_licence or est_parent:
    print("Tu peux emprunter la voiture.")
else:
    print("Tu ne peux pas emprunter la voiture.")
```

Dans ce cas, la condition est vraie si l'utilisateur a une licence **ou** est parent.

### 5. **Les Comparateurs : Pour Rendre Tes Tests Plus Précis**

Les conditions sont souvent basées sur des comparaisons. Python te permet d'utiliser une gamme de comparateurs pour affiner tes décisions.

Les comparateurs de base sont :

- **`==`** : égal à
- **`!=`** : différent de
- **`>`** : plus grand que
- **`<`** : plus petit que
- **`>=`** : plus grand ou égal à
- **`<=`** : plus petit ou égal à

Exemple :

```python
temperature = 30

if temperature > 25:
    print("Il fait chaud.")
elif temperature < 15:
    print("Il fait froid.")
else:
    print("Il fait doux.")
```

Ici, la température est comparée à plusieurs valeurs pour déterminer la phrase à afficher.

### 6. **Les Conditions Imbriquées : Les Décisions à Plusieurs Niveaux**

Les conditions peuvent être imbriquées les unes dans les autres. Cela permet de créer des décisions en plusieurs étapes, où une condition dépend d'une autre.

Exemple :

```python
age = 20
a_licence = True

if age >= 18:
    if a_licence:
        print("Tu peux conduire.")
    else:
        print("Tu es majeur, mais tu n'as pas de licence.")
else:
    print("Tu es mineur.")
```

Ici, il y a deux niveaux de décision : d'abord, on vérifie si l'utilisateur est majeur, puis on vérifie s'il a une licence.

### 7. **Les Expressions Conditionnelles (Ternaires) : La Décision en Une Ligne**

Si tu veux faire une décision rapide sans écrire des blocs complets de `if`/`else`, tu peux utiliser l'**expression conditionnelle**. C’est un moyen plus concis d’écrire des conditions simples.

Exemple :

```python
age = 19
status = "majeur" if age >= 18 else "mineur"
print(status)
```

Ici, la variable `status` reçoit "majeur" si la condition est vraie, sinon "mineur".

### Conclusion

Les structures conditionnelles en Python sont **cruciales** pour écrire des programmes interactifs et réactifs. Que ce soit pour choisir entre plusieurs options, combiner des tests complexes ou prendre des décisions imbriquées, elles te permettent de rendre ton code **intelligent** et **dynamique**.

La prochaine fois que tu écris un programme, n'oublie pas de bien structurer tes décisions pour rendre ton code clair et fluide. Alors, prêt à prendre des décisions comme un pro ?
