---
date: '2025-04-13T04:34:56+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: "🔒 Créer un Gestionnaire de Mots de Passe en CLI avec Python"
description: "Découvrez comment développer un outil sécurisé en ligne de commande pour la gestion de mots de passe avec Python, en appliquant des principes de sécurité, de gestion d'erreurs et de modularité."
categories: ["Projets Python"]
tags: ["Python", "CLI", "Gestion de Mots de Passe"]
---

# Créer un Gestionnaire de Mots de Passe en CLI avec Python

Dans un monde où la sécurité de nos informations personnelles est devenue incontournable, j'ai voulu réaliser un projet simple mais efficace : un gestionnaire de mots de passe en ligne de commande (CLI). Cet outil, développé en Python, permet de générer des mots de passe robustes, de les sauvegarder dans un fichier JSON et de les manipuler via une interface textuelle intuitive. Dans cet article, je vous montre comment quelques dizaines de lignes de code bien structurées peuvent mettre en œuvre des concepts avancés en programmation et en sécurité.

## Le Contexte et le Problème

Nous utilisons quotidiennement de nombreux mots de passe pour protéger nos comptes et nos données sensibles. Il devient alors crucial de disposer d’un outil qui aide à :
- **Générer des mots de passe sécurisés** : En combinant aléatoirement des lettres, des chiffres et des caractères spéciaux.
- **Gérer et stocker ces mots de passe** : Afin d’éviter la réutilisation de mots de passe faibles ou la perte de ceux-ci.
- **Faciliter l’accès** : En permettant de récupérer rapidement le mot de passe associé à un compte via une interface en ligne de commande.

Traditionnellement, les solutions existantes peuvent être lourdes ou complexes pour un usage personnel. C’est là qu’intervient notre gestionnaire de mots de passe en CLI : il est léger, personnalisable et entièrement réalisé en Python.

## La Solution : passwordManager.py

Le script `passwordManager.py` propose une solution complète en offrant les fonctionnalités suivantes :

- **Génération de mots de passe sécurisés**  
  Grâce au module `secrets`, le programme crée des mots de passe forts en combinant lettres, chiffres et caractères spéciaux.

- **Sauvegarde et chargement via JSON**  
  Les mots de passe sont stockés dans un fichier JSON. Le code gère intelligemment les erreurs liées à la lecture du fichier (fichier inexistant ou corrompu) pour assurer une robustesse accrue.

- **Interface en Ligne de Commande avec argparse**  
  Une interface intuitive permet à l’utilisateur d’enregistrer, récupérer, supprimer et lister les mots de passe grâce à des commandes claires (`save`, `get`, `del`, `gen`, `list`).

- **Utilisation du Presse-papiers**  
  L’intégration du module `pyperclip` permet de copier automatiquement le mot de passe récupéré dans le presse-papiers, ce qui simplifie son utilisation.

Voici un extrait de la structure du code :

```python
def generate_password():
    """Générer un mot de passe sécurisé"""
    characters = ''
    if NEED_STRING:
        characters += string.ascii_letters
    if NEED_DIGITS:
        characters += string.digits
    if NEED_SPECIAL_CHARACTERS:
        characters += string.punctuation
    return ''.join(secrets.choice(characters) for _ in range(PASSWORD_LENGTH))
```

Ce passage montre la façon dont la génération de mot de passe est réalisée en tirant profit de la sécurité offerte par le module `secrets`.

## Compétences Python Démontrées

### 1. Programmation modulaire et procédurale
- **Organisation claire du code** : Chaque fonctionnalité (génération, sauvegarde, chargement, suppression) est implémentée dans une fonction dédiée, facilitant la maintenance et l'évolution du projet.
- **Point d'entrée principal** : La fonction `main()` centralise l'exécution du script en s'appuyant sur le module `argparse` pour gérer différentes commandes.

### 2. Gestion des Exceptions et Robustesse du Code
- **Anticipation des erreurs** : La fonction `load_passwords()` intègre des blocs `try-except` pour gérer les erreurs liées à la manipulation de fichiers JSON, assurant la continuité de l’exécution même en cas de problèmes.

### 3. Manipulation de fichiers avec JSON
- **Stockage des données** : La sérialisation et la désérialisation des mots de passe dans un fichier JSON permettent une persistance simple des données, tout en restant facilement consultables et modifiables.

### 4. Sécurité et Génération de Mots de Passe
- **Utilisation du module secrets** : Cette méthode offre une robustesse inégalée dans la génération de chaînes aléatoires, essentielles pour la sécurité des comptes.
- **Configuration flexible** : Les constantes en haut du script permettent d’ajuster rapidement la longueur des mots de passe et le type de caractères utilisés, pour répondre à divers besoins de sécurité.

### 5. Interface en Ligne de Commande
- **Convivialité** : Grâce à `argparse`, l’utilisateur peut interagir avec le programme en utilisant des commandes simples et explicites, rendant l’outil accessible même aux débutants.

## Applications et Perspectives

Ce gestionnaire de mots de passe en CLI représente bien plus qu’un exercice de programmation. En le développant, j'ai pu approfondir ma maîtrise de la sécurité appliquée, de la gestion d'erreurs et des techniques de manipulation de données en Python. 

Dans un contexte professionnel ou personnel, un tel outil peut servir de base à des projets plus ambitieux, par exemple :
- **Intégrer un chiffrement du fichier JSON** pour renforcer la protection des données sensibles.
- **Mettre en place un système de logging** pour mieux diagnostiquer et résoudre d'éventuels problèmes en production.
- **Développer une interface graphique** pour rendre l’outil accessible à un public non technique.

## Conclusion

Réussir à créer un gestionnaire de mots de passe en CLI avec Python est une belle démonstration de l'application concrète de diverses compétences en programmation. Ce projet prouve qu'avec une bonne architecture de code et une attention particulière portée à la sécurité et à la robustesse, il est tout à fait possible de développer des outils efficaces et utiles pour notre quotidien numérique.

Quelles fonctionnalités ajouteriez-vous à ce gestionnaire de mots de passe ? Partagez vos idées et vos retours dans les commentaires. Ensemble, continuons à repousser les limites de ce que nous pouvons réaliser avec Python !

---

📌 **Suivez-moi pour plus de contenus sur Python et le développement logiciel !**  
👉 [Dev.to](https://dev.to/memlenz) / [GitHub](https://github.com/memlenz) / [Twitter](https://twitter.com/achafine)
