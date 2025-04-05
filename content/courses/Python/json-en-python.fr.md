---
date: "2025-04-04T10:55:18+01:00"
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: "Comprendre et maîtriser with et open en Python"
tags: ["python", "with", "open"]
categories: ["Cours Python"]
---

# **Manipulation des fichiers JSON en Python : Maîtrisez l'Art du Stockage de Données**

Les fichiers JSON, c’est **le** format incontournable pour stocker et échanger des données. Ultra flexible, il est utilisé partout : API, configurations, logs, bases de données NoSQL… Bref, **vous allez bosser avec**.

Dans cet article, on va voir **comment manipuler les fichiers JSON en Python** :  
✅ Lire et écrire des fichiers JSON  
✅ Modifier et mettre à jour les données  
✅ Gérer les erreurs et éviter les pièges classiques  
✅ Exercices pratiques pour tester vos skills

---

## **1. Lire un Fichier JSON (`json.load`)**

L’étape de base : **charger** un fichier JSON dans Python.

### **Exemple : Lire un fichier JSON**

Imaginons un fichier `data.json` contenant :

```json
{
  "nom": "Alice",
  "age": 30,
  "ville": "Paris"
}
```

On peut le charger avec :

```python
import json

with open("data.json", "r") as fichier:
    data = json.load(fichier)

print(data["nom"])  # Affiche : Alice
```

🔹 **Explications :**

- `open("data.json", "r")` ouvre le fichier en **lecture** (`r`).
- `json.load(fichier)` transforme le JSON en **dictionnaire Python**.
- On accède ensuite aux données normalement.

💡 **Piège à éviter** : Si le fichier est mal formé, `json.load()` va lever une erreur. **On gère ça juste après.**

---

## **2. Écrire un Fichier JSON (`json.dump`)**

Si vous voulez **sauvegarder des données** dans un fichier JSON, utilisez `json.dump()`.

### **Exemple : Écrire un JSON dans un fichier**

```python
import json

data = {
    "nom": "Bob",
    "age": 25,
    "ville": "Lyon"
}

with open("output.json", "w") as fichier:
    json.dump(data, fichier, indent=4)

print("Données enregistrées !")
```

🔹 **Explications :**

- `open("output.json", "w")` ouvre le fichier en **écriture** (`w`).
- `json.dump(data, fichier, indent=4)` écrit les données dans le fichier, en **format lisible** (`indent=4`).

💡 **Bonus : Formattage lisible avec `sort_keys`**

```python
json.dump(data, fichier, indent=4, sort_keys=True)
```

Cela trie les clés du JSON **par ordre alphabétique**.

---

## **3. Modifier un JSON (Mise à Jour de Données)**

### **🔹 Ajouter une nouvelle clé au JSON et sauvegarder**

```python
import json

with open("data.json", "r") as fichier:
    data = json.load(fichier)

data["email"] = "alice@example.com"  # Ajout d'une nouvelle clé

with open("data.json", "w") as fichier:
    json.dump(data, fichier, indent=4)

print("Mise à jour effectuée !")
```

🔹 **Explications :**

- On **charge** le JSON
- On **ajoute/modifie** une clé
- On **réécrit** tout le JSON dans le fichier

💡 **Bonus : Ajouter un élément dans une liste JSON**

Si `data.json` contient :

```json
{
  "users": ["Alice", "Bob"]
}
```

On peut ajouter `"Charlie"` dans la liste :

```python
data["users"].append("Charlie")

with open("data.json", "w") as fichier:
    json.dump(data, fichier, indent=4)
```

---

## **4. Gérer les Erreurs JSON comme un Pro**

Manipuler des fichiers JSON peut **planter** si :  
❌ Le fichier n’existe pas  
❌ Le JSON est mal formé  
❌ Une clé est absente

📌 **Sécurisation avec `try-except`**

```python
import json

try:
    with open("data.json", "r") as fichier:
        data = json.load(fichier)
    print("Fichier chargé avec succès !")
except FileNotFoundError:
    print("Erreur : Fichier non trouvé !")
except json.JSONDecodeError:
    print("Erreur : Le fichier JSON est mal formé !")
```

✅ **Toujours prévoir des exceptions pour éviter les crashs inutiles.**

---

## **5. Exercices Pratiques 🚀**

### **💡 Exercice 1 : Écrire une fonction `sauvegarder_json(nom_fichier, data)`**

👉 Créez une fonction qui prend un dictionnaire Python et l’enregistre dans un fichier JSON.

**Exemple d’utilisation :**

```python
data = {"nom": "John", "score": 42}
sauvegarder_json("score.json", data)
```

---

### **💡 Exercice 2 : Lire une liste d’objets JSON et l’afficher**

Créez un fichier `users.json` avec :

```json
[
  { "nom": "Alice", "age": 30 },
  { "nom": "Bob", "age": 25 },
  { "nom": "Charlie", "age": 27 }
]
```

Écrivez un script qui charge ce JSON et affiche chaque utilisateur ainsi :

```
Nom: Alice, Âge: 30
Nom: Bob, Âge: 25
Nom: Charlie, Âge: 27
```

📌 **Indice : `json.load()` retourne une liste !**

---

### **💡 Exercice 3 : Ajouter un utilisateur dans le fichier `users.json`**

Écrivez une fonction `ajouter_utilisateur(nom, age)` qui ajoute un nouvel utilisateur à la liste JSON.

**Exemple d’utilisation :**

```python
ajouter_utilisateur("David", 22)
```

💡 **Vérifiez que `users.json` contient bien le nouvel utilisateur !**

---

## **Conclusion : JSON en Python, un Incontournable**

Vous avez maintenant toutes les bases pour manipuler des fichiers JSON comme un **pro**. ✅

**Compétences acquises :**  
✅ Lire et écrire des fichiers JSON  
✅ Modifier et mettre à jour les données  
✅ Gérer les erreurs et exceptions  
✅ Travailler avec des listes d’objets JSON

🚀 **Prochain défi : Implémentez une mini-base de données JSON pour gérer une liste de contacts (nom, téléphone, email).**

Allez, à vous de jouer ! 😎🔥
