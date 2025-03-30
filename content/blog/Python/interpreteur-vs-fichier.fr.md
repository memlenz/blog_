---
date: "2025-03-29T23:37:06+01:00"
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: "Différence entre l’interpréteur Python (Shell interactif) et un fichier Python"
categories: ["Blog Python"]
tags: [Python, Organisation]
---

Quand on commence avec Python, une des premières confusions vient du fait qu’on peut taper des commandes dans un terminal et voir immédiatement un résultat, mais aussi écrire du code dans un fichier `.py`. Pourquoi ces deux modes existent-ils ? Et surtout, quand utiliser l’un ou l’autre ?

---

## **1. L’interpréteur Python : le mode interactif**

L’interpréteur Python, aussi appelé **Shell interactif**, est une interface où on peut taper directement du code Python et voir le résultat immédiatement.

💡 Pour le lancer, il suffit d’ouvrir un terminal et de taper :

```sh
python
```

(Sous certaines installations, il faudra peut-être taper `python3` au lieu de `python`.)

Une fois lancé, l’interpréteur affiche une invite comme celle-ci :

```sh
Python 3.11.2 (default, Feb  8 2023, 10:50:25)
[GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

À partir de là, on peut entrer des instructions Python et voir leur effet immédiatement :

```python
>>> print("Hello, world!")
Hello, world!
```

Chaque ligne est évaluée **instantanément**, ce qui est parfait pour :  
✅ Tester rapidement une idée.  
✅ Expérimenter une fonction ou un bout de code sans créer de fichier.  
✅ Déboguer un comportement précis.

📌 **Limites du Shell interactif** : Dès qu’on ferme l’interpréteur, tout ce qu’on a tapé est perdu. Ce n’est pas pratique pour écrire un programme complet.

---

## **2. Le fichier Python : exécuter un script**

Quand on veut écrire un programme plus structuré, on crée un fichier Python (`.py`).

Par exemple, on peut écrire le contenu suivant dans un fichier `mon_script.py` :

```python
print("Hello, world!")
print("Ce fichier Python est exécuté entièrement.")
```

Puis l’exécuter dans un terminal avec :

```sh
python mon_script.py
```

Cela affichera :

```sh
Hello, world!
Ce fichier Python est exécuté entièrement.
```

🔹 **Pourquoi utiliser un fichier Python ?**  
✅ Pour écrire un programme réutilisable.  
✅ Pour organiser du code sur plusieurs lignes ou fonctions.  
✅ Pour éviter de retaper le même code à chaque fois.

📌 **Différence avec le mode interactif** :

- Dans un fichier, **tout le code est exécuté d’un coup** quand on lance le script.
- Il n’y a pas d’évaluation immédiate ligne par ligne comme dans l’interpréteur.

---

## **3. Quand utiliser l’un ou l’autre ?**

| Mode                    | Avantages                                                         | Inconvénients                                             |
| ----------------------- | ----------------------------------------------------------------- | --------------------------------------------------------- |
| **Interpréteur Python** | Rapide pour tester des idées, pas besoin d’enregistrer un fichier | Tout est perdu à la fermeture                             |
| **Fichier Python**      | Permet de structurer et enregistrer du code réutilisable          | Nécessite de relancer le script après chaque modification |

💡 **Règle simple** :

- Si c’est juste pour tester une ligne de code ➝ **utilise l’interpréteur**.
- Si tu veux créer un vrai programme ➝ **écris un fichier Python**.

---

## **Conclusion**

L’interpréteur Python et les fichiers `.py` servent des objectifs différents mais complémentaires. **L’interpréteur est parfait pour des tests rapides, tandis que les fichiers sont indispensables pour écrire un vrai programme.** En comprenant cette différence dès le début, on évite pas mal de confusions et on apprend à coder plus efficacement. 🚀
