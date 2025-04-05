---
date: "2025-03-31T10:55:18+01:00"
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: "Comprendre et maîtriser argparse en Python"
tags: ["python", "cli", "argparse"]
categories: ["Python", "Tutoriels"]
---

# 🚀 Maîtriser argparse en Python : Guide complet

> **🔥 Pourquoi ce tuto ?**
>
> - Tu veux faire des scripts **en ligne de commande** propres et puissants ?
> - Marre de `sys.argv` et du parsing manuel des arguments ?
> - Tu veux **des options, des flags, de l'aide automatique, et même des sous-commandes** ?

---

## 📌 Pourquoi `argparse` et pas `sys.argv` ?

🔥 _Comment un script Python récupère-t-il des arguments en ligne de commande ?_  
Si tu fais juste :

```python
import sys

print(sys.argv)
```

et que tu lances :

```bash
python3 script.py hello world
```

Tu obtiens :

```bash
['script.py', 'hello', 'world']
```

🤔 Problèmes avec `sys.argv` :

- **Tout est en `str`** (tu dois tout convertir à la main)
- **Pas de validation automatique** (si on attend un `int` et que l'utilisateur entre `hello`, ça plante)
- **Aucune aide** (`--help` n'existe pas)
- **Difficile à maintenir** (si tu rajoutes plein d’options, c'est vite le chaos)

🔥 **Solution** : `argparse`, qui gère tout ça **automatiquement** !

---

## 🚀 1. Ton premier script avec `argparse`

**On commence simple** : un script qui prend un **nom** et un flag `--verbose`.

```python
import argparse

parser = argparse.ArgumentParser(description="Un script simple avec argparse")
parser.add_argument("nom", help="Votre nom")
parser.add_argument("-v", "--verbose", action="store_true", help="Mode verbeux")

args = parser.parse_args()

print(f"Salut {args.nom} !")
if args.verbose:
    print("Mode verbeux activé.")
```

🔥 Teste avec :

```bash
python3 script.py Alice
# → Salut Alice !

python3 script.py Bob --verbose
# → Salut Bob !
# → Mode verbeux activé.
```

---

## ⚙️ 2. Ajouter des options avec valeurs (`type`, `default`, `choices`)

On veut un script qui prend :

- **Un nom** (obligatoire)
- **Un âge** (optionnel, mais doit être un `int`)
- **Une ville** (optionnelle, par défaut `"Inconnue"`)
- **Un niveau** (optionnel, parmi `"débutant"`, `"intermédiaire"`, `"expert"`)

```python
import argparse

parser = argparse.ArgumentParser(description="Un script amélioré avec argparse")

parser.add_argument("nom", help="Votre nom")
parser.add_argument("-a", "--age", type=int, help="Votre âge")
parser.add_argument("--ville", default="Inconnue", help="Votre ville")
parser.add_argument("--niveau", choices=["débutant", "intermédiaire", "expert"], help="Votre niveau")

args = parser.parse_args()

print(f"Salut {args.nom} !")
if args.age:
    print(f"Tu as {args.age} ans.")
print(f"Tu es à {args.ville}.")
if args.niveau:
    print(f"Niveau : {args.niveau}")
```

🔥 Teste avec :

```bash
python3 script.py Alice -a 25 --ville Paris --niveau expert
# → Salut Alice !
# → Tu as 25 ans.
# → Tu es à Paris.
# → Niveau : expert.
```

---

## 🛠️ 3. Ajouter plusieurs sous-commandes (`subparsers`)

On veut un script **multi-fonction** avec :

- `ajouter` → pour ajouter un utilisateur
- `supprimer` → pour supprimer un utilisateur

On va utiliser les **subparsers**, qui permettent de créer des sous-commandes comme `git commit`, `git push`, etc.

```python
import argparse

parser = argparse.ArgumentParser(description="Gestion des utilisateurs")
subparsers = parser.add_subparsers(dest="commande", help="Commandes disponibles")

# Commande "ajouter"
ajouter_parser = subparsers.add_parser("ajouter", help="Ajouter un utilisateur")
ajouter_parser.add_argument("nom", help="Nom de l'utilisateur")
ajouter_parser.add_argument("-a", "--age", type=int, help="Âge de l'utilisateur")

# Commande "supprimer"
supprimer_parser = subparsers.add_parser("supprimer", help="Supprimer un utilisateur")
supprimer_parser.add_argument("nom", help="Nom de l'utilisateur à supprimer")

args = parser.parse_args()

if args.commande == "ajouter":
    print(f"Ajout de {args.nom}")
    if args.age:
        print(f"Âge : {args.age}")

elif args.commande == "supprimer":
    print(f"Suppression de {args.nom}")
```

🔥 Teste avec :

```bash
python3 script.py ajouter Alice -a 30
# → Ajout de Alice
# → Âge : 30

python3 script.py supprimer Alice
# → Suppression de Alice

python3 script.py --help
# → Affiche les commandes disponibles
```

🔥 **Pourquoi `subparsers` ?**

- Permet de structurer **plus proprement** les scripts complexes.
- Fonctionne comme `git add`, `git commit`, etc.
- Gère l’aide `--help` **automatiquement** pour chaque sous-commande.

---

## 📜 4. Générer une aide automatique

🔥 Un gros avantage d'`argparse` ? Il génère une aide **automatique** avec `--help` !

Teste simplement :

```bash
python3 script.py --help
```

Ou pour une sous-commande :

```bash
python3 script.py ajouter --help
```

Ça affiche **tous les arguments disponibles** sans que tu aies à écrire la doc à la main. 🏆

---

## 🔥 5. Récapitulatif et bonnes pratiques

✅ **Utilise `argparse.ArgumentParser(description="...")`** → Pour bien décrire ton script.  
✅ **Utilise des options `-f`, `--flag`, `type`, `default`, `choices`** → Pour plus de flexibilité.  
✅ **Ajoute `parser.add_subparsers(dest="commande")`** → Pour gérer des **sous-commandes**.  
✅ **Toujours tester `--help`** → C'est généré automatiquement et ça aide l'utilisateur.

---

## 🎯 TL;DR : Le script ultime avec `argparse`

```python
import argparse

parser = argparse.ArgumentParser(description="Gestion des utilisateurs")
subparsers = parser.add_subparsers(dest="commande", help="Commandes disponibles")

ajouter_parser = subparsers.add_parser("ajouter", help="Ajouter un utilisateur")
ajouter_parser.add_argument("nom", help="Nom de l'utilisateur")
ajouter_parser.add_argument("-a", "--age", type=int, help="Âge de l'utilisateur")

supprimer_parser = subparsers.add_parser("supprimer", help="Supprimer un utilisateur")
supprimer_parser.add_argument("nom", help="Nom de l'utilisateur à supprimer")

args = parser.parse_args()

if args.commande == "ajouter":
    print(f"Ajout de {args.nom}, âge : {args.age or 'Non spécifié'}")
elif args.commande == "supprimer":
    print(f"Suppression de {args.nom}")
```

🔥 **Maintenant, tes scripts Python sont prêts pour la production !** 🚀
