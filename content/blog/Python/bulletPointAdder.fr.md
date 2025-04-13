---
date: "2025-04-09T21:29:56+01:00"
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: "🎯 Implémentation d'un foramateur de texte en python"
description: "Découvrez comment manipuler des chaines de caractère en python pour créer des listes"
categories: ["Projets Python",]
tags: ["Python", "Algorithmie"]
---

# Maîtriser la Manipulation de Texte avec Python : Création d'un Formateur de Liste à Puces

Dans l'environnement de travail numérique d'aujourd'hui, formater du texte rapidement et efficacement peut faire gagner un temps précieux. En tant que développeur Python, j'ai récemment créé un outil utilitaire qui démontre comment quelques lignes de code Python peuvent simplifier les tâches quotidiennes. Laissez-moi vous présenter mon script de formatage de listes à puces et mettre en évidence les compétences Python qu'il illustre.

## Le Problème

Nous avons tous été confrontés à cette situation - copier du texte provenant de diverses sources qui nécessite un reformatage avant utilisation. Peut-être extrayez-vous des éléments d'un e-mail, d'un document ou d'une page web et souhaitez-vous les transformer en une liste à puces propre. Faire cela manuellement est fastidieux, surtout avec des textes plus longs.

## La Solution : bulletPointAdder.py

Ma solution est un script Python simple mais puissant qui prend du texte depuis votre presse-papiers, formate chaque ligne avec des puces et replace le résultat dans votre presse-papiers - prêt à être collé où vous en avez besoin.

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-
"""
    Nom du fichier : bulletPointAdder.py
    Description : Formate du texte pour obtenir une liste à puce
    Auteur : ADEBI Châ-Fine Ayédoun achafine@gmail.com
    Date : 2025-04-08
"""
```

## Compétences Python Démontrées

### 1. Utilisation de Bibliothèques Externes

Le script utilise `pyperclip`, une bibliothèque tierce qui fournit une fonctionnalité de presse-papiers multiplateforme :

```python
import pyperclip
```

Cela démontre une connaissance de l'écosystème Python et comment tirer parti des bibliothèques existantes pour étendre les fonctionnalités sans réinventer la roue.

### 2. Maîtrise des Expressions Régulières

L'une des fonctionnalités les plus puissantes du script est sa capacité de traitement de texte utilisant des expressions régulières :

```python
REGEX = r'^[\d\.\)\s\-_]+'  # Motif pour correspondre à divers formats de numérotation
line = re.sub(REGEX, '', line)
```

Ce motif regex identifie et supprime différents types de numérotation ou formats de puces qui pourraient déjà exister dans le texte. Il gère les listes numérotées (comme "1. Élément"), la numérotation entre parenthèses (comme "1) Élément"), et divers styles de puces.

### 3. Constantes pour la Configuration

Le script utilise des constantes pour rendre les changements de configuration faciles et centralisés :

```python
# Constantes
BULLET = '.'  # Vos nouvelles lignes peuvent commencer par: '•', '-', '*', '→'
REGEX = r'^[\d\.\)\s\-_]+'  # Vous pouvez changer la logique des lignes
```

Cette approche suit le principe de séparation de la configuration et de la logique, rendant le code plus maintenable.

### 4. Décomposition en Fonctions et Principes de Code Propre

Le script est divisé en fonctions claires, à objectif unique :

```python
def paste_from_clipboard() -> str:
    """On récupère le contenu du clipboard"""
    
def bullet_point_adder() -> str:
    """On modifie chaque ligne pour en faire des listes à puces"""
    
def paste_to_clipboard() -> None:
    """On copie le contenu dans le clipboard"""
```

Chaque fonction a une responsabilité claire, rendant le code plus facile à comprendre, tester et maintenir.

### 5. Annotations de Type

Le code utilise les annotations de type de Python pour indiquer les types de retour des fonctions :

```python
def paste_from_clipboard() -> str:
```

Cela rend le code plus autodocumenté et permet un meilleur support d'outils et une meilleure détection d'erreurs.

### 6. Manipulation et Formatage de Chaînes

Le script démontre une maîtrise des opérations sur les chaînes :

```python
line = f'{BULLET} {line}'  # f-strings pour un formatage de chaîne propre
return '\n'.join(formated_lines)  # Joindre des listes en chaînes
welcome.center(len(welcome) + 5, '*')  # Alignement et remplissage de chaînes
```

Ces techniques montrent une connaissance des riches capacités de manipulation de chaînes de Python.

### 7. Compréhension de Liste et Itération

Bien que n'utilisant pas directement les compréhensions de liste, le code traite efficacement les listes par itération :

```python
formated_lines = []
for line in list_content:
    # Logique de traitement
    formated_lines.append(line)
```

### 8. Gestion des Erreurs

Le bloc d'exécution principal inclut une gestion appropriée des exceptions :

```python
try:
    # Traitement principal
except Exception as e:
    print(f"Erreur : {str(e)}")
```

Cela garantit que le script gère élégamment les erreurs potentielles plutôt que de planter.

### 9. Docstrings et Documentation

Chaque fonction inclut des docstrings appropriées expliquant son objectif :

```python
def bullet_point_adder() -> str:
    """On modifie chaque ligne pour en faire des listes à puces"""
```

De plus, l'en-tête du script fournit des métadonnées sur l'auteur, l'objectif et la date.

### 10. Structure de Programme Appropriée

Le script suit la convention Python d'utilisation de la garde `if __name__ == "__main__":` pour séparer le code exécutable des modules importables :

```python
if __name__ == "__main__":
    # Code d'exécution ici
```

Cela permet au script d'être importé comme un module sans exécuter la fonctionnalité principale.

## Application dans le Monde Réel

Ce script peut être simple, mais il démontre comment Python peut être utilisé pour automatiser des tâches routinières. Par exemple, si vous préparez une présentation et devez formater une liste d'éléments, ou si vous prenez des notes et souhaitez les convertir rapidement en format à puces, cet outil fait gagner du temps et assure la cohérence.

## Conclusion

Créer de petits scripts utilitaires comme `bulletPointAdder.py` est une excellente façon d'affiner vos compétences Python tout en créant des outils qui rendent votre flux de travail quotidien plus efficace. Le script présente une gamme de techniques Python, de la manipulation basique de chaînes aux expressions régulières, le tout enveloppé dans un programme propre et bien structuré.

Quelles tâches quotidiennes automatisez-vous avec Python ? J'aimerais entendre parler de vos scripts utilitaires dans les commentaires !

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-
"""
    Nom du fichier : bulletPointAdder.py
    Description : Formate du texte pour obtenir une liste à puce
    Auteur : ADEBI Châ-Fine Ayédoun achafine@gmail.com
    Date : 2025-04-08
"""


import re
import pyperclip


# Constantes
BULLET = '.'  # Vos nouvelles lignes peuvent commencer par: '•', '-', '*', '→'
REGEX = r'^[\d\.\)\s\-_]+'  # Vous pouvez changer le la logique des lignes


def paste_from_clipboard() -> str:
    """On récupère le contenu du clipboard"""
    return pyperclip.paste()


def bullet_point_adder() -> str:
    """On modifie chaque ligne pour en faire des listes à puces"""
    content = paste_from_clipboard().strip()
    # On convertis le contenu en liste
    list_content = content.split('\n')
    # Formatage des lignes
    formated_lines = []
    for line in list_content:
        line = line.strip()
        # Gestion des lignes vides
        if not line:
            formated_lines.append(line)
            continue
        # Gestion des lignes qui commencent par des chiffres
        line = re.sub(REGEX, '', line)
        # Ajout des puces
        if not line.startswith(BULLET):
            line = f'{BULLET} {line}'
        formated_lines.append(line)
    return '\n'.join(formated_lines)


def paste_to_clipboard() -> None:
    """On copie le contenu dans le clipboard"""
    pyperclip.copy(bullet_point_adder())


if __name__ == "__main__":
    welcome = "Welcome to the Bullet Point Adder"
    print(welcome.center(len(welcome) + 5, '*'))
    try:
        print("Processing".ljust(len(welcome)+5, '.'))
        paste_to_clipboard()
        print("successfully paste".center(len(welcome) + 5, '*'))
    except Exception as e:
        print(f"Erreur : {str(e)}")
```
---


📌 **Follow me for more Python and dev content!**  
👉 [[Dev.to](https://dev.to/memlenz) / [GitHub](https://github.com/memlenz) / [Twitter Profile](https://twitter.com/achafine)]
