---
title: "Différence entre un fichier .py et un exécutable .exe"
date: 2025-03-29
description: "Comprendre la différence entre un fichier Python (.py) et une application exécutable (.exe)."
categories: [Python, Débutant]
tags: [Python, Exécutable, Compilation, Débutant]
---

## **C'est quoi un fichier .py par rapport à une application .exe ?**

Quand on débute en programmation, on peut penser qu’un fichier `.py` (lorsque notre fichier contient du code python) est une application comme un `.exe`. En réalité, ils sont très différents ! Voici une explication claire pour bien comprendre.

---

### **📌 Un fichier `.py`, c’est juste du code source**

Un fichier `.py` contient **du texte** écrit en Python. **Seul l’interpréteur Python sait lire et exécuter ce fichier.**

#### **💡 Exemple :**

Si tu crées un fichier `script.py` contenant :

```python
print("Hello, world!")
```

Ce fichier ne peut pas s'exécuter tout seul. Il faut utiliser **Python** pour l'exécuter :

```bash
python script.py # ou python3 script..py
```

Le `.py` n'est donc **pas un programme autonome**, mais juste un script qui doit être interprété.

---

### **📌 Un fichier `.exe`, c'est un programme exécutable autonome**

Un `.exe` est un fichier qui **peut être exécuté directement sans dépendre d’un autre logiciel**. Il contient du **code machine** que ton ordinateur peut comprendre et exécuter tout seul.

#### **💡 Exemple :**

Si tu télécharges `notepad.exe`, tu peux double-cliquer dessus et ça s’ouvre directement. Il n’a pas besoin d’un autre programme pour fonctionner.

Un `.exe` est donc **un fichier compilé** à partir d'un code source (ex: C, C++, Python compilé) pour qu’il tourne tout seul.

---

### **📌 Différences principales**

| 📂 **Fichier `.py`**                             | ⚙️ **Fichier `.exe`**                              |
| ------------------------------------------------ | -------------------------------------------------- |
| Contient du code Python (lisible par un humain). | Contient du code binaire (illisible).              |
| Besoin d'un interpréteur Python pour s’exécuter. | Peut être exécuté directement sans dépendance.     |
| Facile à modifier (juste du texte).              | Modifiable seulement avec un décompilateur.        |
| Multi-plateforme (Windows, Linux, Mac).          | Spécifique à un OS (Windows `.exe`, Linux `.elf`). |

---

### **📌 Peut-on transformer un `.py` en `.exe` ?**

Oui ! Tu peux **"convertir" un script Python en `.exe`** pour qu’il soit utilisable sans installer Python. On appelle ça un **binaire compilé**.

#### **💡 Exemple avec `pyinstaller` :**

```bash
pip install pyinstaller
pyinstaller --onefile script.py
```

Cela génère un fichier `script.exe` que tu peux exécuter sans Python installé sur la machine.

🚨 **Attention** : Le `.exe` généré reste dépendant de l’OS (Windows/Linux/Mac).

---

## **Conclusion**

- Un fichier `.py` est du code source Python, **non exécutable directement**.
- Un `.exe` est un fichier **compilé**, exécutable sans Python.
- Pour transformer un `.py` en `.exe`, on utilise un outil comme `pyinstaller`.

Maintenant, tu sais pourquoi un fichier `.py` ne fonctionne pas comme un `.exe` et comment les rendre autonomes ! 🚀
