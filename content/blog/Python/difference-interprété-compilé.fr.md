---
title: "Différence entre un langage interprété et un langage compilé"
draft: false
author: "Ayédoun Châ-Fine ADEBI"
date: "2025-03-29T23:09:59+01:00"
description: "Comprendre la différence entre un langage interprété comme Python et un langage compilé comme C."
categories: ["Blog Python"]
tags: [Python, Compilation, Interpréteur, Débutant]
---

## **Langage interprété vs langage compilé : Quelle est la différence ?**

Quand on commence à apprendre la programmation, on entend souvent parler de **langages interprétés** et **langages compilés**, mais la distinction entre les deux n'est pas toujours claire. Pourquoi doit-on **compiler** un programme en C alors que Python fonctionne immédiatement après l’avoir écrit ? Dans cet article, on va **déconstruire cette différence** et voir comment elle impacte l’exécution des programmes.

---

## **1. Définition simple**

Un **langage interprété** exécute le code **ligne par ligne** grâce à un programme spécial appelé **interpréteur**.  
Un **langage compilé** transforme tout le code source en un **fichier exécutable** avant de pouvoir l’exécuter.

---

## **2. Comment ça fonctionne ?**

### 🔹 **Langage interprété (Python, JavaScript, Bash, Ruby, PHP...)**

💡 _Le code est exécuté directement sans passer par une phase de compilation._

1. Tu écris un fichier `.py` contenant du code Python.
2. L’interpréteur Python **lit et exécute** le code **ligne par ligne**.
3. Il n’y a pas de compilation préalable, mais l’exécution est plus lente qu’un programme compilé.

📌 **Exemple en Python :**

```python
print("Hello, world!")
```

➡ Tu peux taper ce code directement dans le terminal Python (`python`), et il s’exécute immédiatement.

---

### 🔹 **Langage compilé (C, C++, Rust, Go...)**

💡 _Le code est transformé en un fichier exécutable avant d’être lancé._

1. Tu écris un fichier `.c` (par exemple en C).
2. Un **compilateur** traduit tout le code en un **fichier exécutable** (ex : `mon_programme.exe` sous Windows ou `a.out` sous Linux).
3. Tu peux exécuter ce fichier **sans avoir besoin du langage installé** sur la machine.

📌 **Exemple en C :**

```c
#include <stdio.h>

int main() {
    printf("Hello, world!\n");
    return 0;
}
```

➡ Compilation du programme :

```sh
gcc mon_programme.c -o mon_programme
```

➡ Exécution :

```sh
./mon_programme
```

---

## **3. Principales différences**

| 🔹 Critère                       | ⚡ Langage interprété (Python)                            | 🚀 Langage compilé (C)                                                      |
| -------------------------------- | --------------------------------------------------------- | --------------------------------------------------------------------------- |
| 📜 **Exécution**                 | Ligne par ligne avec un interpréteur                      | Tout le code est traduit en une seule fois                                  |
| 🏎️ **Vitesse**                   | Plus lent car chaque ligne est analysée en temps réel     | Plus rapide car le programme est déjà transformé en code machine            |
| 💻 **Portabilité**               | Fonctionne sur toutes les machines où Python est installé | Peut nécessiter une recompilation pour chaque système (Windows, Linux, Mac) |
| 🛠️ **Facilité de développement** | Plus simple pour débuter, pas besoin de compilation       | Plus complexe, il faut compiler et gérer les erreurs avant l’exécution      |

---

## **4. Cas particulier : Java (Compilé et interprété ?)**

Java est un cas un peu spécial :

1. Il est **compilé** en un format intermédiaire appelé **bytecode** (`.class`).
2. Ce bytecode est ensuite **interprété** par la **JVM (Java Virtual Machine)** sur chaque ordinateur.

✅ **Avantage** : Un seul fichier `.class` peut fonctionner sur toutes les machines disposant d’une JVM, sans recompilation.

---

## **5. En résumé : Quel impact pour toi ?**

- **Si tu veux coder vite et tester immédiatement ton code**, un langage **interprété** comme Python est idéal.
- **Si tu cherches de la performance et un exécutable autonome**, un langage **compilé** comme C ou Rust sera plus adapté.

En Python, on ne se soucie pas de compilation : **il suffit d’écrire et d’exécuter immédiatement**. C’est pourquoi c’est un langage souvent recommandé aux débutants.

---

🎯 **Et toi, tu préfères coder en langage interprété ou compilé ? Partage ton avis en commentaire !** 🚀
