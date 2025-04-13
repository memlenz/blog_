---
date: "2025-02-26T02:26:44+01:00"
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: "Variables et commentaires en python"
description: "Apprenez les variables et commentaires en python"
tags: ["python", "variables"]
categories: ["Cours Python"]
---

# Les Variables en Python : Le cœur de ton code

Les variables sont comme des boîtes magiques qui servent à stocker et manipuler des données dans ton programme. En Python, elles sont particulièrement souples et intuitives !

## 🧠 Qu'est-ce qu'une variable ?

Une variable en Python est comme un conteneur étiqueté qui peut stocker différents types de données :

- 📦 Stocke des valeurs (nombres, texte, listes...)
- 🏷️ Possède un nom qui permet d'y accéder
- 🔄 Peut changer de contenu au cours du programme

---

### 🎯 Mission #1 : Explorer les variables

Testez ce code dans l'interpréteur Python et observez :

```python
age = 25
nom = "Alice"
print(f"Bonjour, je m'appelle {nom} et j'ai {age} ans.")
age = 26
print(f"C'est mon anniversaire ! Maintenant j'ai {age} ans.")
```

<details>
<summary>📝 Explication du code</summary>

1. On crée une variable `age` contenant le nombre 25
2. On crée une variable `nom` contenant le texte "Alice"
3. On affiche un message utilisant ces deux variables
4. On change la valeur de `age` à 26
5. Le message suivant reflète cette nouvelle valeur
</details>

---

## 🧩 Types de variables en Python

Python est intelligent et détermine automatiquement le type de variable selon la valeur qu'on lui assigne.

### 📊 Les types fondamentaux

| Type               | Exemple         | Description    |
| ------------------ | --------------- | -------------- |
| `str` (chaîne)     | `"Hello"`       | Texte          |
| `int` (entier)     | `42`            | Nombre entier  |
| `float` (flottant) | `3.14`          | Nombre décimal |
| `bool` (booléen)   | `True`, `False` | Vrai ou faux   |

### 🔢 Les types de collections

| Type                  | Exemple                       | Description                                |
| --------------------- | ----------------------------- | ------------------------------------------ |
| `list` (liste)        | `[1, 2, 3]`                   | Collection ordonnée modifiable             |
| `tuple` (tuple)       | `(1, 2, 3)`                   | Collection ordonnée non modifiable         |
| `dict` (dictionnaire) | `{"nom": "Alice", "age": 25}` | Paires clé-valeur                          |
| `set` (ensemble)      | `{"pomme", "banane"}`         | Collection non ordonnée d'éléments uniques |

---

## 🛠️ Manipulation des variables

### 📝 Création et modification

```python
# Création de variables
score = 0
nom_joueur = "Aventurier"

# Modification de variables
score = score + 10  # score vaut maintenant 10
score += 5          # score vaut maintenant 15
```

### 🪄 Assignation multiple

Python permet d'assigner plusieurs variables en une seule ligne :

```python
x, y, z = 10, 20, 30
print(x, y, z)  # Affiche: 10 20 30

# Échange de valeurs en une ligne !
a, b = 5, 10
a, b = b, a  # a vaut 10, b vaut 5
```

---

## 📏 Règles de nommage

Pour nommer tes variables, respecte ces règles :

✅ **Autorisé** :

- Lettres (a-z, A-Z)
- Chiffres (sauf en première position)
- Underscore (\_)

❌ **Interdit** :

- Commencer par un chiffre
- Utiliser des espaces
- Utiliser des caractères spéciaux (@, #, %, etc.)
- Utiliser des mots réservés Python (`if`, `for`, `while`, etc.)

### 🌟 Bonnes pratiques

```python
# 👍 Bon nommage
age_joueur = 25
prix_total = 49.99
est_actif = True

# 👎 Mauvais nommage
a = 25         # Nom pas clair
pT = 49.99     # Abréviation peu lisible
variable1 = True  # Nom générique
```

---

## 🧪 Variables mutables vs immuables

### 🔒 Types immuables (non modifiables après création)

- `int`, `float`, `str`, `bool`, `tuple`

```python
texte = "Hello"
# texte[0] = "h"  # ❌ Erreur ! Les strings sont immuables
```

### 🔓 Types mutables (modifiables après création)

- `list`, `dict`, `set`

```python
fruits = ["pomme", "banane", "cerise"]
fruits[0] = "fraise"  # ✅ Fonctionne ! Les listes sont mutables
print(fruits)  # ['fraise', 'banane', 'cerise']
```

---

## 🔍 Portée des variables

### 🌍 Variables globales

Accessibles partout dans le programme

```python
score_total = 0  # Variable globale

def ajouter_points(points):
    global score_total  # Indique qu'on utilise la variable globale
    score_total += points

ajouter_points(10)
print(score_total)  # Affiche 10
```

### 🏠 Variables locales

Existent uniquement dans une fonction

```python
def calculer_aire():
    longueur = 5  # Variable locale
    largeur = 3   # Variable locale
    return longueur * largeur

print(calculer_aire())  # Affiche 15
# print(longueur)  # ❌ Erreur ! Variable non définie ici
```

---

## 🎮 Défis pratiques

### 🏆 Défi #1 : Convertisseur de température

Créez un fichier `convertisseur.py` :

1. Il demande à l'utilisateur d'entrer une température en Celsius.
2. Il convertit cette température en Fahrenheit en utilisant la formule : \( \text{Fahrenheit} = (\text{Celsius} \times \frac{9}{5}) + 32 \).
3. Il affiche le résultat de la conversion.
4. Ensuite, il demande à l'utilisateur d'entrer une température en Fahrenheit.
5. Il convertit cette température en Celsius en utilisant la formule : \( \text{Celsius} = (\text{Fahrenheit} - 32) \times \frac{5}{9} \).
6. Il affiche le résultat de cette conversion.

### Exemple d'output

Si l'utilisateur entre `25` pour la température en Celsius et `77` pour la température en Fahrenheit, l'output sera :

```
Température en Celsius : 25
25.0°C = 77.0°F
Température en Fahrenheit : 77
77.0°F = 25.0°C
```

Les valeurs affichées peuvent varier en fonction des entrées de l'utilisateur.

<details>
<summary> # Convertisseur Celsius ↔ Fahrenheit </summary>

```python
celsius = float(input("Température en Celsius : "))

# Conversion en Fahrenheit

fahrenheit = (celsius * 9/5) + 32

# Affichage du résultat

print(f"{celsius}°C = {fahrenheit}°F")

# Bonus : conversion inverse

temp_f = float(input("Température en Fahrenheit : "))
temp_c = (temp_f - 32) * 5/9
print(f"{temp_f}°F = {temp_c}°C")
```

</details>

### 🏆 Défi #2 : Générateur de profil

Créez un fichier `profil.py` :

```python
# Collecte d'informations
nom = input("Ton nom : ")
age = int(input("Ton âge : "))
ville = input("Ta ville : ")
hobby = input("Ton hobby préféré : ")

# Calculs dérivés
annee_naissance = 2025 - age
est_majeur = age >= 18

# Génération du profil
print("\n===== PROFIL AVENTURIER =====")
print(f"Nom: {nom}")
print(f"Âge: {age} ans (né(e) vers {annee_naissance})")
print(f"Localisation: {ville}")
print(f"Passion: {hobby}")
print(f"Statut: {'Majeur' if est_majeur else 'Mineur'}")
print("============================")
```

---

## 💡 Astuces avancées

### 🔍 Vérifier le type d'une variable

```python
x = 42
print(type(x))  # <class 'int'>

y = "Bonjour"
print(type(y))  # <class 'str'>
```

### 🧮 Opérations sur les variables

```python
a = 5
b = 2

print(a + b)    # Addition: 7
print(a - b)    # Soustraction: 3
print(a * b)    # Multiplication: 10
print(a / b)    # Division: 2.5
print(a // b)   # Division entière: 2
print(a % b)    # Modulo (reste): 1
print(a ** b)   # Puissance: 25
```

---

## 📚 Pour aller plus loin

- Explore les f-strings pour des affichages plus élégants
- Découvre les listes, dictionnaires et tuples pour stocker des collections
- Apprends à combiner des variables avec des conditions et des boucles

---

## 🎯 Mémo pratique

✅ Les variables sont des "boîtes" pour stocker des données  
✅ Python détermine automatiquement leur type  
✅ Elles peuvent changer de valeur au cours du programme  
✅ Choisis des noms significatifs pour tes variables  
✅ Certains types sont modifiables, d'autres non

---

Prêt à expérimenter avec les variables ? Essaye les défis ci-dessus et vois comment ces "boîtes magiques" peuvent rendre ton code plus dynamique et puissant !
