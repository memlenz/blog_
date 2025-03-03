---
date: '2025-03-03T05:46:06+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: 'Les Classes en Python'
description: "Comprendre les classes et objets en Python"
tags: ["Python", "Classes", "Objets"]
categories: ["Cours Python"]
---


Si t’as déjà croisé des mots comme *POO*, *classes*, *objets* et que ça t’a donné envie de fuir… t’inquiète, on va rendre ça simple et digeste. La programmation orientée objet (*POO* pour les intimes) est une manière d’organiser ton code pour qu’il soit plus réutilisable, propre et logique.  

Allez, c’est parti.  

---

## **1. C’est quoi une classe, c’est quoi un objet ?**  

Si Python était un jeu vidéo, une *classe* serait le plan détaillé d’un personnage (*genre un modèle 3D avec toutes ses capacités et stats*), et un *objet* serait une instance réelle de ce personnage en jeu.  

En d’autres termes :  
- Une *classe* définit la structure et le comportement (c’est le moule).
- Un *objet* est une copie spécifique créée à partir de cette classe (c’est le gâteau issu du moule).  

Prenons un exemple concret :  

```python
class Chat:
    def __init__(self, nom, couleur):
        self.nom = nom
        self.couleur = couleur

    def miauler(self):
        return f"{self.nom} : Miaouuuu !"

# Création d’objets (des chats spécifiques)
chat1 = Chat("Whiskers", "Gris")
chat2 = Chat("Garfield", "Orange")

print(chat1.miauler())  # Whiskers : Miaouuuu !
print(chat2.miauler())  # Garfield : Miaouuuu !
```

Ici :  
- `Chat` est une classe.  
- `chat1` et `chat2` sont des objets (des instances de la classe `Chat`).  
- Chaque objet a ses propres caractéristiques (`nom`, `couleur`).  
- `miauler()` est une méthode (*un truc qu’un chat peut faire*).  

---

## **2. Le constructeur `__init__` : Le boulanger du code**  

Le `__init__` est la fonction qui est appelée automatiquement quand tu crées un objet. Il sert à donner des valeurs initiales aux attributs de l’objet.  

```python
class Chien:
    def __init__(self, nom, race):
        self.nom = nom
        self.race = race

    def aboyer(self):
        return f"{self.nom} : Wouf Wouf !"

chien1 = Chien("Rex", "Berger Allemand")
print(chien1.aboyer())  # Rex : Wouf Wouf !
```

Dès qu’on fait `Chien("Rex", "Berger Allemand")`, Python appelle `__init__` en arrière-plan pour créer notre chien.

---

## **3. Attributs et méthodes : La sauce de la POO**  

Les attributs sont les *données* de l’objet (*nom, couleur, race…*).  
Les méthodes sont les *actions* que l’objet peut effectuer (*miauler, aboyer…*).  

Tu peux aussi avoir des **attributs de classe** (*communs à toutes les instances*).  

```python
class Humain:
    espece = "Homo sapiens"  # Attribut de classe

    def __init__(self, nom, age):
        self.nom = nom  # Attribut d’instance
        self.age = age  # Attribut d’instance

humain1 = Humain("Alice", 25)
humain2 = Humain("Bob", 30)

print(humain1.espece)  # Homo sapiens
print(humain2.espece)  # Homo sapiens
```

---

## **4. Héritage : Quand une classe en recycle une autre**  

L’héritage permet de créer une classe en reprenant une autre et en y ajoutant des modifications. Un peu comme une mise à jour d’un perso dans un jeu.  

```python
class Animal:
    def __init__(self, nom):
        self.nom = nom

    def parler(self):
        return "Je fais un bruit d'animal"

# Le Chat hérite de Animal
class Chat(Animal):
    def parler(self):
        return f"{self.nom} : Miaouuu !"

chat1 = Chat("Felix")
print(chat1.parler())  # Felix : Miaouuu !
```

Ici, `Chat` hérite de `Animal`, donc il a accès à `nom` et peut *overrider* (redéfinir) `parler()`.

---

## **5. Encapsulation : Protéger ses données comme un boss**  

L’encapsulation, c’est cacher certaines données pour éviter qu’elles soient modifiées n’importe comment.  

```python
class CompteBancaire:
    def __init__(self, titulaire, solde):
        self.titulaire = titulaire
        self.__solde = solde  # Attribut privé (avec __ devant)

    def deposer(self, montant):
        self.__solde += montant

    def afficher_solde(self):
        return f"Solde de {self.titulaire} : {self.__solde}€"

compte = CompteBancaire("John", 1000)
compte.deposer(500)
print(compte.afficher_solde())  # Solde de John : 1500€

# print(compte.__solde)  # Erreur, on ne peut pas y accéder directement !
```

Le `__solde` est privé, donc il ne peut pas être modifié n’importe comment en dehors de la classe.

---

## **6. Polymorphisme : Quand les objets s’adaptent**  

Le polymorphisme, c’est la capacité pour des objets de classes différentes d’utiliser une même méthode mais avec des comportements différents.  

```python
class Chien:
    def parler(self):
        return "Wouf !"

class Chat:
    def parler(self):
        return "Miaou !"

# Utilisation polymorphique
animaux = [Chien(), Chat()]

for animal in animaux:
    print(animal.parler())  
# Wouf !
# Miaou !
```

Ici, `parler()` fonctionne pour `Chien` et `Chat`, mais différemment.

---

## **Conclusion : La POO, c’est pas si compliqué**  

Si on résume :  
✅ Une **classe** est un plan, un **objet** est une instance de ce plan.  
✅ Le **constructeur `__init__`** sert à initialiser les objets.  
✅ Les **attributs** sont les données, les **méthodes** sont les actions.  
✅ L’**héritage** permet de réutiliser du code.  
✅ L’**encapsulation** protège certaines données sensibles.  
✅ Le **polymorphisme** permet d’avoir une même méthode avec différents comportements.  

Avec ça, t’as une base solide pour comprendre la POO en Python. Reste plus qu’à pratiquer 💪.
