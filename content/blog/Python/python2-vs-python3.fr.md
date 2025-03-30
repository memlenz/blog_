---
title: "Python 2 vs Python 3 : Pourquoi c’est important ?"
draft: false
author: "Ayédoun Châ-Fine ADEBI"
date: "2025-04-17T23:09:59+01:00"
description: "Comprendre la différence entre Python 2 et Python 3, et pourquoi il ne faut plus utiliser Python 2."
categories: ["Blog Python"]
tags: [Python, Versions, Interpréteur, Débutant]
---

## **Python 2 vs Python 3 : Un duel dépassé ?**

Si tu débutes en Python, tu as peut-être déjà vu des références à **Python 2** et **Python 3**. Pourtant, la plupart des tutoriels d'aujourd'hui parlent uniquement de Python 3. Alors, c'est quoi cette histoire ? Pourquoi il y avait deux versions majeures ? Et surtout, **est-ce que ça te concerne en 2025 ?**

### **Un peu d’histoire**

Python a été créé en **1991** par **Guido van Rossum**, et pendant longtemps, **Python 2 était la norme**. Mais en 2008, une nouvelle version majeure est sortie : **Python 3**. Le problème ? Python 3 n'était pas **rétrocompatible**, c'est-à-dire qu'un programme écrit en Python 2 ne fonctionnait **pas forcément** en Python 3.

### **Python 2 : Un dinosaure encore vivant ?**

Pendant plus de 10 ans, beaucoup de développeurs ont **refusé de passer à Python 3** parce que leurs projets étaient bloqués en Python 2. Mais en **2020**, Python 2 est officiellement **mort** : **plus de mises à jour, plus de support, plus de corrections de sécurité.**

👉 **Si tu commences aujourd’hui, oublie Python 2.**

### **Les vraies différences entre Python 2 et 3**

| **Catégorie**  | **Python 2**                  | **Python 3**                 |
| -------------- | ----------------------------- | ---------------------------- |
| Support        | Abandonné en 2020 ⚠️          | Actif et recommandé ✅       |
| `print`        | `print "Hello"` ❌            | `print("Hello")` ✅          |
| `input()`      | `raw_input()` et `input()` 🤯 | Juste `input()` ✅           |
| Unicode        | Texte en ASCII par défaut ❌  | Texte en UTF-8 par défaut ✅ |
| Division (`/`) | `5 / 2 = 2` ❌ (arrondi)      | `5 / 2 = 2.5` ✅ (correct)   |

En gros, **Python 3 corrige tous les défauts de Python 2** et apporte plein d'améliorations.

### **Pourquoi on en parle encore ?**

Certains **anciens** projets sont encore en Python 2, donc si tu bosses sur un vieux code, tu pourrais y être confronté. Mais à **99%**, tu peux ignorer Python 2.

### **Conclusion : Python 3, point final**

- **Python 2 est mort, ne l’apprends pas.**
- **Python 3 est plus simple, plus puissant et mieux supporté.**
- **Si tu tombes sur du vieux code en Python 2, essaye de le convertir en Python 3.**

Bref, si quelqu’un te parle encore de Python 2 aujourd’hui... réponds-lui juste : **"C’est fini, frérot."** 😆
