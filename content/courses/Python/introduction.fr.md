---
date: '2025-02-25T01:59:02+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: "Introduction à Python"
tags: ["python", "débutant", "introduction"]
categories: ["Cours Python"]
description: "Découvrez ce qu'est Python, ses caractéristiques et comment l'installer."
series_order: 0
---

### **Introduction à Python**  

#### **1. Qu'est-ce que Python ?**  
Python est un **langage de programmation de haut niveau** connu pour sa **simplicité** et sa **lisibilité**. Il est utilisé dans de nombreux domaines :  
✅ Développement web  
✅ Data Science et Machine Learning  
✅ Automatisation et scripting  
✅ Cybersécurité, etc.  

Quelques caractéristiques de Python :  
- **Interprété** : le code s'exécute ligne par ligne.  
- **Multi-paradigme** : supporte la programmation procédurale, orientée objet et fonctionnelle.  
- **Écosystème riche** : une large collection de bibliothèques (Django, NumPy, etc.).  

👉 **À lire** :  
- [The Zen of Python](https://peps.python.org/pep-0020/) 📜  
- [Documentation officielle](https://docs.python.org/3/tutorial/index.html) 📚  

---

#### **2. Installation de Python**  
1. **Vérifier si Python est déjà installé**  
   - Ouvrez un terminal et tapez :  
     ```sh
     python --version
     ```  
   - Ou, selon votre système :  
     ```sh
     python3 --version
     ```  

2. **Installer Python**  
   - 📌 **Windows/Mac** : [Télécharger Python](https://www.python.org/downloads/)  
   - 📌 **Linux (Debian/Ubuntu)** :  
     ```sh
     sudo apt update && sudo apt install python3
     ```  
   - 📌 **Linux (Void Linux)** :  
     ```sh
     sudo xbps-install -S python3
     ```  

---

#### **3. Tester l'interpréteur Python**  
Une fois installé, testons l'interpréteur :  
```sh
python3
```  
Une invite interactive s'affiche :  
```python
>>> print("Hello, World!")
Hello, World!
```  

💡 **L’interpréteur Python permet d’exécuter des commandes en temps réel**, utile pour tester rapidement du code.