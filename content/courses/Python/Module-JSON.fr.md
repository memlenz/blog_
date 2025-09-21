---
date: '2025-03-04T01:37:05+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: 'Module JSON'
description: "Maîtriser le module JSON en Python"
tags: ["Python", "Module", "JSON"]
categories: ["Cours Python"]
series: ["Apprendre Python"]
series_order: 25
---

JSON (*JavaScript Object Notation*) est un format ultra-populaire pour échanger des données. Léger, lisible et facile à parser, il est utilisé partout : API, bases de données, fichiers de configuration... Bref, si vous codez en Python, vous allez souvent bosser avec du JSON.  

Heureusement, Python nous simplifie la vie avec son module **`json`**, un outil puissant pour convertir des objets Python en JSON (sérialisation) et vice versa (désérialisation). On va voir ça en détail, avec des exemples concrets pour que vous soyez **OP sur JSON**. 🔥  

---

## **1. Importation du Module JSON**  

Le module `json` est inclus **de base** en Python, donc pas besoin d’installation supplémentaire. Un simple :  

```python
import json
```  

Et vous êtes **prêt à tout casser** ! 🚀  

---

## **2. Convertir un Dictionnaire Python en JSON (`json.dumps`)**  

La fonction **`json.dumps()`** transforme un objet Python en une **chaîne JSON**.  

```python
import json

data = {
    "nom": "John",
    "age": 25,
    "ville": "Paris",
    "est_étudiant": False
}

json_str = json.dumps(data)
print(json_str)  
# {"nom": "John", "age": 25, "ville": "Paris", "est_étudiant": false}
```

🔹 **Points importants :**  
- Les booléens (`True` et `False`) deviennent respectivement `true` et `false` en JSON.  
- Les dictionnaires Python (`dict`) sont directement convertibles en JSON.  
- `dumps()` **ne stocke pas** les données dans un fichier, il retourne juste une chaîne JSON.  

### **🔹 Formatage lisible (`indent`, `sort_keys`)**  
Le JSON brut, c’est bien. Lisible, c’est mieux !  

```python
json_str = json.dumps(data, indent=4, sort_keys=True)
print(json_str)
```

📌 **Explications :**  
- `indent=4` ajoute une **indentation de 4 espaces** pour un affichage propre.  
- `sort_keys=True` trie les clés **par ordre alphabétique**.  

---

## **3. Convertir du JSON en Dictionnaire Python (`json.loads`)**  

La fonction **`json.loads()`** permet de convertir une chaîne JSON en objet Python.  

```python
json_str = '{"nom": "Alice", "age": 30, "ville": "Lyon"}'
data = json.loads(json_str)

print(data["nom"])  # Alice
print(type(data))  # <class 'dict'>
```

📌 **Pourquoi c’est utile ?**  
- Quand on récupère des données JSON d’une **API** ou d’un **fichier**, `json.loads()` permet de les manipuler comme un **dictionnaire Python**.  

---

## **4. Lire et Écrire un Fichier JSON (`json.dump` & `json.load`)**  

### **🔹 Sauvegarder un dictionnaire dans un fichier JSON (`json.dump`)**  
Si vous voulez stocker des données sous forme de JSON, `json.dump()` est là pour ça :  

```python
with open("data.json", "w") as file:
    json.dump(data, file, indent=4)
```

🔹 **Différence avec `json.dumps()` ?**  
- `json.dumps()` **retourne** une chaîne JSON.  
- `json.dump()` **écrit directement** dans un fichier.  

### **🔹 Charger un fichier JSON (`json.load`)**  
On peut ensuite lire notre fichier JSON avec `json.load()` :  

```python
with open("data.json", "r") as file:
    data = json.load(file)

print(data)
```

📌 **Pourquoi c’est pratique ?**  
- Utile pour **charger des configurations**, des **paramètres d'application**, ou des **données utilisateur**.  

---

## **5. Sérialiser des Objets Personnalisés (`default`)**  

Que se passe-t-il si on veut **convertir un objet custom en JSON** ?  

```python
class Personne:
    def __init__(self, nom, age):
        self.nom = nom
        self.age = age

p = Personne("Max", 22)

# ERREUR !
print(json.dumps(p))  
```

Python ne sait pas comment convertir `Personne` en JSON. On doit lui expliquer :  

```python
def convert_obj(obj):
    if isinstance(obj, Personne):
        return {"nom": obj.nom, "age": obj.age}
    raise TypeError("Type non sérialisable")

print(json.dumps(p, default=convert_obj))
```

✅ Maintenant, ça fonctionne ! **Alternative plus propre** :  

```python
import json

class Personne:
    def __init__(self, nom, age):
        self.nom = nom
        self.age = age

    def to_dict(self):
        return {"nom": self.nom, "age": self.age}

p = Personne("Max", 22)
print(json.dumps(p, default=lambda o: o.to_dict(), indent=4))
```

---

## **6. Désérialiser des Objets Personnalisés (`object_hook`)**  

On peut aussi récupérer un objet **à partir du JSON** :  

```python
json_str = '{"nom": "Max", "age": 22}'

def json_to_personne(d):
    return Personne(d["nom"], d["age"])

p = json.loads(json_str, object_hook=json_to_personne)
print(p.nom, p.age)  # Max 22
```

---

## **7. Gérer les Erreurs JSON**  

⚠️ Les JSON mal formés peuvent provoquer des erreurs. Toujours prévoir une gestion d’erreur !  

```python
json_str = '{"nom": "Max", "age": 22'  # Manque une accolade !

try:
    data = json.loads(json_str)
except json.JSONDecodeError as e:
    print("Erreur JSON :", e)
```

---

## **8. Cas Pratiques : JSON dans la Vraie Vie 🚀**  

### **🔹 Charger un fichier de configuration**
Beaucoup d'applications stockent leurs paramètres dans un **fichier JSON** :  

```python
import json

with open("config.json") as file:
    config = json.load(file)

print(config["theme"])  # Exemple : "dark mode"
```

### **🔹 API et JSON**
Quand on interagit avec une API en Python (via `requests`), on obtient souvent des **réponses JSON**. Exemple :  

```python
import requests

response = requests.get("https://jsonplaceholder.typicode.com/users/1")
data = response.json()

print(data["name"])  # Le nom de l'utilisateur
```

---

## **Conclusion**  

Le module `json` est un **outil essentiel** pour tout dev Python. Il permet de :  
✅ Convertir facilement des **objets Python en JSON** et inversement.  
✅ Manipuler des **fichiers JSON** pour le stockage de données.  
✅ Sérialiser et désérialiser des **objets personnalisés**.  
✅ **Interagir avec des API** qui retournent du JSON.  

Bref, si vous bossez avec des données, vous allez utiliser `json`. **Testez-le dès maintenant en écrivant un mini-système de sauvegarde en JSON !** 🚀🔥  

---

🎯 **Prochain Défi :** Implémentez une mini-base de données en JSON pour stocker et récupérer des contacts (nom, email, téléphone). 💡
