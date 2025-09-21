---
date: '2025-03-03T05:53:56+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: 'Polymorphisme'
description: "Comprendre et Maîtriser le polymorphisme en Python"
tags: ["Python", "Polymorphisme"]
categories: ["Cours Python"]
series: ["Apprendre Python"]
series_order: 20
---


T’as déjà entendu parler du polymorphisme en Python, mais ça te semble encore flou ? Imagine un ninja qui change de technique en fonction de son adversaire : le polymorphisme, c’est un peu ça en programmation. Il permet d’utiliser une même interface pour différents types d’objets, rendant ton code plus flexible et réutilisable.  

---

### **1. C’est quoi le polymorphisme ?**  
En gros, c’est la capacité d’un objet à se comporter différemment selon son contexte. En Python, ça s’applique surtout aux classes et aux méthodes qui peuvent être redéfinies sans changer leur nom.  

### **2. Le polymorphisme avec les classes**  
En POO, t’as des classes parent et enfant. L’idée, c’est que les classes enfant peuvent redéfinir des méthodes tout en gardant le même nom. Exemple classique avec des animaux :  

```python
class Animal:
    def parler(self):
        pass  # Méthode à redéfinir

class Chien(Animal):
    def parler(self):
        return "Wouf!"

class Chat(Animal):
    def parler(self):
        return "Miaou!"

# Utilisation polymorphique
animaux = [Chien(), Chat()]

for animal in animaux:
    print(animal.parler())  # Chaque animal réagit selon son type
```

💡 **Ici, `parler()` est redéfini pour chaque animal, mais on l’appelle de la même façon.**  

---

### **3. Le polymorphisme avec les fonctions**  
Les fonctions en Python peuvent accepter des objets différents tant qu’ils respectent un certain contrat. Pas besoin de définir un type strict, Python est dynamique !  

```python
def faire_parler(animal):
    print(animal.parler())

faire_parler(Chien())  # Wouf!
faire_parler(Chat())   # Miaou!
```

Python s’en fiche du type exact de `animal`, tant qu’il a une méthode `parler()`. C’est ce qu’on appelle le **duck typing** : "Si ça marche comme un canard, alors c’est un canard".  

---

### **4. Le polymorphisme avec les opérateurs**  
Tu peux aussi redéfinir le comportement des opérateurs (`+`, `-`, etc.) grâce aux **méthodes magiques**.  

```python
class Point:
    def __init__(self, x, y):
        self.x, self.y = x, y

    def __add__(self, other):
        return Point(self.x + other.x, self.y + other.y)

    def __str__(self):
        return f"({self.x}, {self.y})"

p1 = Point(2, 3)
p2 = Point(4, 1)

print(p1 + p2)  # (6, 4)
```

🔹 **Ici, on redéfinit `+` pour additionner des objets `Point` au lieu de simples nombres.**  

---

### **5. Pourquoi utiliser le polymorphisme ?**  
✅ Code plus propre et maintenable  
✅ Réduction du copier-coller (DRY : Don’t Repeat Yourself)  
✅ Plus de flexibilité dans le design  

Le polymorphisme, c’est un outil puissant quand tu veux coder de manière modulaire et évolutive. Au lieu d’écrire des conditions à rallonge du genre `if isinstance(obj, TypeX): ...`, tu laisses Python gérer ça pour toi.  

---

### **Conclusion**  
Si tu veux écrire du code propre et scalable, le polymorphisme est ton allié. Il te permet d'écrire du code générique tout en gérant des cas spécifiques sans te casser la tête.  

💡 **Retiens juste que tant qu’un objet répond à la bonne méthode, Python le considère valide, peu importe son type !**  

T’as capté ? Maintenant, applique ça dans tes projets et deviens un ninja du code ! 🚀
