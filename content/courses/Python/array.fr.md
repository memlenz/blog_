---
date: '2025-03-03T05:40:20+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: 'Les array en Python'
description: "Maîtriser les arrays Python"
tags: ["Python", "Array"]
categories: ["Cours Python"]
series: ["Apprendre Python"]
series_order: 17
---


Les **arrays** en Python, c’est un peu le truc que tout le monde confond avec les listes. Pourtant, ce sont deux structures bien différentes, et si tu veux vraiment coder efficacement, autant comprendre quand utiliser l’un ou l’autre.  

---

## 1. **Les Arrays en Python, c’est quoi ?**  

En Python, on a les listes `list`, qui sont hyper flexibles, et on a aussi les **arrays**, qui viennent du module `array`.  

🔹 **Différence clé ?**  
- Une liste (`list`) peut contenir des types différents.  
- Un `array.array`, lui, ne stocke que des éléments du **même type** (entiers, flottants, etc.).  

Si tu viens de C ou C++, un `array.array` ressemble plus à un tableau classique qu’une liste Python.  

---

## 2. **Pourquoi utiliser `array` au lieu d’une liste ?**  

👉 **Performance** : Un `array.array` prend moins de mémoire et est plus rapide pour certaines opérations.  
👉 **Contraintes de type** : Pas d’accident en mélangeant les types (tu évites les erreurs bizarres).  
👉 **Interopérabilité** : Si tu bosses avec des données binaires ou du C, c’est souvent plus simple.  

Mais si tu cherches encore plus de performance, tu devrais plutôt regarder **NumPy**, qui est un monstre dans le domaine des tableaux optimisés.  

---

## 3. **Créer et manipuler un `array`**  

D’abord, faut importer le module :  

```python
import array  
```

Ensuite, on crée un array. Il faut spécifier un code de type (par ex. `'i'` pour les entiers signés) :  

```python
arr = array.array('i', [1, 2, 3, 4, 5])  # Tableau d'entiers
print(arr)
```

📌 **Quelques codes de type utiles :**  
- `'i'` → entier signé (4 octets)  
- `'f'` → flottant (4 octets)  
- `'d'` → double flottant (8 octets)  
- `'b'` → entier signé (1 octet)  

---

## 4. **Manipuler un `array`**  

Ajouter des éléments :  
```python
arr.append(6)  # Ajoute 6 à la fin
arr.insert(2, 10)  # Insère 10 à l’index 2
print(arr)  # [1, 2, 10, 3, 4, 5, 6]
```

Supprimer un élément :  
```python
arr.remove(3)  # Supprime la première occurrence de 3
print(arr)
```

Accéder aux éléments :  
```python
print(arr[0])  # Premier élément
print(arr[-1]) # Dernier élément
```

Itérer sur l’array :  
```python
for val in arr:
    print(val)
```

---

## 5. **Les limites des `array` et pourquoi NumPy est souvent meilleur**  

Là où `array.array` est un peu limité, **NumPy** explose tout. Si tu dois bosser avec des données numériques, évite `array` et fonce sur NumPy.  

Exemple avec NumPy :  

```python
import numpy as np  

arr_np = np.array([1, 2, 3, 4, 5])
print(arr_np * 2)  # Multiplication vectorielle (plus rapide et optimisée)
```

Avec un `array.array`, t’aurais eu une **erreur** si tu tentais de multiplier par 2 directement.  

---

## 6. **Conclusion : Quand utiliser `array` ?**  

✅ Si tu veux juste un tableau optimisé avec un seul type de données, `array` est un bon choix.  
✅ Si tu bosses avec de gros calculs numériques ou des matrices, **NumPy est bien meilleur**.  
✅ Si tu veux de la flexibilité, reste avec les listes Python (`list`).  

En gros :  
- **Débutant ou projet standard ?** → Utilise une liste.  
- **Besoin de performances et d’optimisation mémoire ?** → `array.array`.  
- **Données scientifiques et calculs avancés ?** → NumPy.  

T’as capté l’idée. 🚀
