---
date: "2025-04-03T10:55:18+01:00"
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: "Comprendre et maîtriser with et open en Python"
tags: ["python", "with", "open"]
categories: ["Cours Python"]
series: ["Apprendre Python"]
series_order: 30
---

# **`with open()` en Python : Gérer les fichiers comme un pro**

Quand on bosse avec des fichiers en Python, la méthode classique c’est d’ouvrir le fichier, lire ou écrire dedans, puis le refermer. Mais soyons honnêtes, **qui pense toujours à fermer proprement son fichier ?** 🤨

C’est là que `with open()` entre en scène :

- **Plus besoin de se soucier de `close()`**
- **Moins de bugs liés aux fichiers non fermés**
- **Code plus propre et plus lisible**

C’est parti pour une exploration rapide et efficace. 🚀

---

## **1. Lire un fichier avec `with open()`**

### 🔹 **Méthode classique (à éviter)**

```python
f = open("mon_fichier.txt", "r")
contenu = f.read()
f.close()  # Oublié = fuite de ressources !
print(contenu)
```

Si le script plante avant `close()`, le fichier **reste ouvert** et peut causer des soucis.

---

### 🔹 **Méthode propre avec `with open()`**

```python
with open("mon_fichier.txt", "r") as fichier:
    contenu = fichier.read()

print(contenu)  # Le fichier est fermé automatiquement après le bloc `with`
```

✅ **Avantages :**

- Le fichier se **ferme automatiquement**, même en cas d’erreur.
- Pas besoin d’appeler `close()`, Python le fait pour nous.

---

## **2. Lire un fichier ligne par ligne**

Lire tout le fichier avec `read()` peut être **inefficace** si c’est un gros fichier.  
➡️ **Solution : lire ligne par ligne**

```python
with open("mon_fichier.txt", "r") as fichier:
    for ligne in fichier:
        print(ligne.strip())  # `strip()` pour enlever les sauts de ligne inutiles
```

---

## **3. Écrire dans un fichier (`"w"`)**

Le mode `"w"` **écrase** le fichier s’il existe déjà.

```python
with open("nouveau_fichier.txt", "w") as fichier:
    fichier.write("Hello, world !\n")
    fichier.write("Ligne 2 du fichier.\n")
```

📌 **Attention :** Tout contenu précédent sera effacé.

---

## **4. Ajouter du texte (`"a"`)**

Le mode `"a"` **ajoute** du texte sans écraser le fichier existant.

```python
with open("nouveau_fichier.txt", "a") as fichier:
    fichier.write("Une nouvelle ligne ajoutée !\n")
```

---

## **5. Lire et écrire (`"r+"`)**

Le mode `"r+"` permet de **lire et écrire** dans un fichier existant.

```python
with open("nouveau_fichier.txt", "r+") as fichier:
    contenu = fichier.read()
    fichier.write("\nAjout d'une ligne en mode lecture/écriture.")
```

📌 **Piège !** L’écriture commence à la fin de la dernière lecture.

---

## **Exercice Pratique : Création d’un journal de logs**

🔥 **Objectif :** Écrire un programme qui enregistre chaque action dans un fichier `log.txt` avec un horodatage.

### 🛠 **Instructions :**

1. À chaque exécution du script, une nouvelle ligne est ajoutée au fichier `log.txt`.
2. La ligne doit contenir la date et l’heure actuelle + un message.
3. Utiliser `with open()` pour gérer l’écriture du fichier.

---

### **💡 Solution :**

```python
from datetime import datetime

# Générer le message de log
timestamp = datetime.now().strftime("%Y-%m-%d %H:%M:%S")
message = f"{timestamp} - Script exécuté avec succès.\n"

# Écrire dans le fichier log
with open("log.txt", "a") as fichier:
    fichier.write(message)

print("Log enregistré !")
```

📌 **À tester** : Exécutez plusieurs fois le script et regardez le contenu de `log.txt`. 🧐

---

## **Conclusion**

✔ `with open()` simplifie la gestion des fichiers et évite les oublis de `close()`.  
✔ C’est **plus sécurisé** et **plus propre** qu’un simple `open()`.  
✔ On peut **lire, écrire et ajouter** du contenu selon le mode choisi (`"r"`, `"w"`, `"a"`, `"r+"` …).

🚀 **Prochain challenge** : créez un script qui stocke les scores d’un jeu et affiche le meilleur score à chaque exécution ! 💡
