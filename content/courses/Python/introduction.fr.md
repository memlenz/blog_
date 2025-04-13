---
date: "2025-02-25T01:59:02+01:00"
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: "Introduction à Python"
tags: ["python", "débutant", "introduction"]
categories: ["Cours Python"]
description: "Découvrez ce qu'est Python, ses caractéristiques et comment l'installer."
series_order: 0
---

# Python : Introduction et premiers pas

Python est un **langage de programmation de haut niveau** qui se distingue par sa **simplicité** et sa **lisibilité**.

## 🐍 Qu'est-ce que Python ?

Python est un langage polyvalent utilisé dans de nombreux domaines :

- 🌐 Développement web
- 📊 Data Science et Machine Learning
- 🤖 Automatisation et scripting
- 🔒 Cybersécurité
- 🎮 Développement de jeux

---

### 🎯 Mission #1 : Déchiffrer le code

Avant d'aller plus loin, examinez ce bout de code et essayez de deviner ce qu'il fait :

```python
nom = input("Quel est ton nom ? ")
print(f"Enchanté, {nom} !")
```

_Réfléchissez quelques instants..._

<details>
<summary>📝 Révéler l'explication</summary>

Ce code demande votre nom via la console et vous salue personnellement. Il illustre parfaitement la simplicité et la lisibilité de Python !

</details>

---

## 🔍 Les caractéristiques qui rendent Python spécial

- **Interprété** : Exécution ligne par ligne, sans compilation préalable
- **Indentation significative** : L'espacement structure le code (pas de { } comme en Java/C++)
- **Multi-paradigme** : Supporte la programmation procédurale, orientée objet et fonctionnelle
- **Batteries included** : Riche bibliothèque standard prête à l'emploi
- **Communauté active** : Écosystème vaste de bibliothèques tierces (Django, NumPy, Pygame, etc.)

## 🛠️ Installation de Python

### 🔄 Vérification préalable

Ouvrez un terminal et tapez l'une des commandes suivantes :

```sh
python --version
```

ou

```sh
python3 --version
```

### 📥 Installation selon votre système

<details>
<summary>🪟 Windows</summary>

1. Téléchargez l'installateur sur [python.org](https://www.python.org/downloads/)
2. Lancez l'installation
3. **Important** : Cochez la case "Add Python to PATH"
4. Suivez les instructions d'installation
</details>

<details>
<summary>🍎 macOS</summary>

1. Téléchargez l'installateur sur [python.org](https://www.python.org/downloads/)
2. Lancez l'installation
3. Suivez les instructions d'installation
</details>

<details>
<summary>🐧 Linux (Debian/Ubuntu)</summary>

```sh
sudo apt update && sudo apt install python3
```

</details>

<details>
<summary>⚡ Linux (Void Linux)</summary>

```sh
sudo xbps-install -S python3
```

</details>

<details>
<summary>⚡ Linux (Arch Linux)</summary>

```sh
sudo pacman -S python3
```

</details>

---

## 🚀 Premier contact avec Python

### 🔮 L'interpréteur interactif

Lancez Python en mode interactif :

```sh
python3 # Ou python selon le système et vous appuyez sur Entrer
```

Vous verrez apparaître l'invite de commande Python `>>>`. C'est votre laboratoire d'expérimentation !

```python
>>> print("Hello, World!")
Hello, World!
>>> 2 + 3
5
>>> "Python" * 3
'PythonPythonPython'
```

Pour quitter l'interpréteur, tapez `exit()` ou utilisez `Ctrl+D` (Unix) ou `Ctrl+Z` puis Enter (Windows).

### 📝 Créer et exécuter un fichier Python

1. Créez un fichier nommé `premier_script.py` :

```python
# Mon premier script Python
print("Bienvenue dans l'aventure Python !")

# Un calcul simple
resultat = 7 * 6
print(f"7 × 6 = {resultat}")

# Interaction avec l'utilisateur
nom = input("Comment t'appelles-tu, aventurier ? ")
print(f"Ravi de te rencontrer, {nom} ! Ton voyage Python commence !")
```

2. Exécutez-le depuis le terminal :

```sh
python3 premier_script.py
```

---

## 🎮 Défis pratiques

### 🏆 Défi #1 : Personnalisation

Dans l'interpréteur Python, créez une phrase de bienvenue personnalisée :

```python
nom = "Alice"  # Remplacez par votre prénom
age = 25       # Remplacez par votre âge
passion = "la programmation"  # Remplacez par votre passion

message = f"Je m'appelle {nom}, j'ai {age} ans et j'adore {passion}."
print(message)
```

### 🏆 Défi #2 : Calculatrice simple

Créez un fichier `calculatrice.py` :

```python
# Mini calculatrice Python
print("🧮 Calculatrice Python 🧮")

premier_nombre = float(input("Premier nombre : "))
deuxieme_nombre = float(input("Deuxième nombre : "))

print(f"Addition : {premier_nombre + deuxieme_nombre}")
print(f"Soustraction : {premier_nombre - deuxieme_nombre}")
print(f"Multiplication : {premier_nombre * deuxieme_nombre}")

# Éviter la division par zéro
if deuxieme_nombre != 0:
    print(f"Division : {premier_nombre / deuxieme_nombre}")
else:
    print("Division par zéro impossible !")
```

---

## 📚 Pour progresser

### 🎓 Ressources incontournables

- [The Zen of Python](https://peps.python.org/pep-0020/) - La philosophie Python
- [Documentation officielle](https://docs.python.org/3/tutorial/index.html) - Le guide de référence
- [Exercism](https://exercism.org/tracks/python) - Défis pratiques pour tous niveaux

### 🧩 Prochaines étapes

- [Configurer votre environnement de développement]({{< relref "blog/python/environnement-de-travail/" >}})
- [Comprendre la différence entre fichier et shell]({{<relref "blog/python/interpreteur-vs-fichier/">}})

---

## 💡 Le saviez-vous ?

Python tire son nom de... la troupe comique Monty Python ! Son créateur, Guido van Rossum, était fan de "Monty Python's Flying Circus" et a choisi ce nom pour rendre son langage amusant et accessible.

---

Prêt à continuer l'aventure ? Utilisez les défis ci-dessus comme point de départ et explorez le vaste monde de Python !
