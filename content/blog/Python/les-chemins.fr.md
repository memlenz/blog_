---
title: "Comprendre les chemins système sous Windows, Linux et macOS"
draft: false
author: "Ayédoun Châ-Fine ADEBI"
date: "2025-04-20T23:09:59+01:00"
description: "Tout ce qu'il faut savoir sur les chemins système et comment ils affectent l'exécution de Python sur Windows, Linux et macOS."
categories: ["Blog Python"]
tags: [Python, Chemins, PATH, Terminal, Débutant]
---

## **Introduction : Pourquoi les chemins système sont importants ?**

Quand on installe Python et qu’on essaie de l’exécuter, on peut se retrouver face à un message frustrant du genre :

```sh
python : commande introuvable
```

Ou pire encore, sous Windows :

```cmd
'python' n’est pas reconnu en tant que commande interne ou externe, un programme exécutable ou un fichier de commandes.
```

C’est là qu’interviennent les **chemins système**. Un chemin système, c’est simplement l’adresse d’un fichier ou d’un dossier sur ton disque dur. Et si ton terminal ne trouve pas Python, c'est probablement parce qu'il ne sait pas **où** le chercher.

---

## **1. Comprendre les chemins sous Windows, Linux et macOS**

Chaque système d'exploitation a sa propre façon de gérer les chemins et de retrouver un programme.

### **Windows : Chemins absolus, relatifs et le PATH**

Sous Windows, un chemin peut ressembler à ça :

```text
C:\Users\TonNom\AppData\Local\Programs\Python\python.exe
```

On distingue :

- **Les chemins absolus** : le chemin complet vers un fichier ou un programme.
- **Les chemins relatifs** : un chemin qui commence à partir du dossier où on se trouve (`.\monfichier.py`).
- **Le PATH** : une liste d’endroits où Windows va chercher les programmes quand tu tapes une commande (`python` par exemple).

💡 **Problème courant** : Si `python` n’est pas reconnu, c’est que son chemin n’est pas dans le `PATH`.

#### **Comment ajouter Python au PATH sous Windows ?**

1. Ouvre une invite de commande (`Win + R`, tape `cmd`, et valide).
2. Tape :
   ```sh
   echo %PATH%
   ```
   Ça affiche tous les répertoires où Windows cherche des programmes.
3. Si le chemin de Python n'est pas dedans, ajoute-le manuellement :
   - **Rechercher** "Variables d’environnement" dans le menu Démarrer.
   - Modifier la variable `Path` et ajouter :
     ```
     C:\Users\TonNom\AppData\Local\Programs\Python\
     ```
4. Redémarre le terminal et teste à nouveau :
   ```sh
   python --version
   ```

---

### **Linux & macOS : Tout est un fichier**

Sous Linux/macOS, les chemins ressemblent à ça :

```text
/home/tonnom/.local/bin/python3
```

Ou sur macOS :

```text
/Library/Frameworks/Python.framework/Versions/3.11/bin/python3
```

Ici, **tout est un fichier**, même les programmes.

#### **Vérifier si Python est installé**

Ouvre un terminal et tape :

```sh
which python3
```

Si Python est installé, ça renverra son chemin. Sinon, il faut l’installer (`sudo apt install python3` sur Debian/Ubuntu).

#### **Le PATH sous Linux/macOS**

Linux/macOS utilisent une variable similaire à Windows pour savoir où chercher les programmes :

```sh
echo $PATH
```

Si Python n’est pas détecté, on peut ajouter son chemin dans `.bashrc` ou `.zshrc` :

```sh
export PATH="$HOME/.local/bin:$PATH"
```

Ensuite, recharge le terminal :

```sh
source ~/.bashrc  # ou source ~/.zshrc
```

---

## **Conclusion**

Les chemins système sont la clé pour exécuter des programmes correctement. Que tu sois sur **Windows, Linux ou macOS**, comprendre comment fonctionne `PATH` t’évitera bien des galères !

Si tu as des erreurs, vérifie toujours :
✔️ Où Python est installé (`where python` sous Windows, `which python3` sous Linux/macOS).  
✔️ Si son chemin est bien dans la variable `PATH`.  
✔️ Si ton terminal est bien redémarré après les changements.

---

💡 **Prochain article : Comment organiser ses scripts Python proprement sur chaque OS ?**
