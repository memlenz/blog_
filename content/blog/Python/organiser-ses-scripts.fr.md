---
title: "Organiser ses scripts Python proprement sur chaque OS"
draft: false
author: "Ayédoun Châ-Fine ADEBI"
date: "2025-04-25T23:09:59+01:00"
description: "Comment structurer ses fichiers et dossiers Python efficacement sous Windows, Linux et macOS."
categories: ["Blog Python"]
tags: [Python, Organisation, Fichiers, OS]
---

## Pourquoi organiser ses scripts Python ?

Quand on commence à coder en Python, on a souvent tendance à tout mettre en vrac sur le bureau ou dans `Documents/`. Mauvaise idée. Une bonne organisation des fichiers et dossiers évite le chaos et facilite la gestion des projets.

Chaque OS (Windows, Linux, macOS) a ses propres conventions pour structurer ses scripts Python proprement. Voyons comment faire ça bien.

---

## 1. Organisation recommandée (indépendante de l'OS)

Peu importe le système, une bonne structure générale pourrait ressembler à ceci :

```plaintext
📁 MesProjetsPython/
   ├── 📁 projet1/
   │   ├── main.py
   │   ├── utils.py
   │   ├── requirements.txt
   │   └── README.md
   ├── 📁 projet2/
   ├── 📁 scripts_utiles/
   │   ├── convertisseur.py
   │   ├── nettoyeur_logs.py
   ├── 📁 envs/ (environnements virtuels)
   ├── 📁 archives/
   └── README.md
```

- **Chaque projet a son propre dossier** (`projet1/`, `projet2/`).
- **Les scripts indépendants sont regroupés** (`scripts_utiles/`).
- **Les environnements virtuels sont isolés** (`envs/`).
- **Les anciens projets peuvent être archivés** (`archives/`).

---

## 2. Où placer son dossier Python selon l’OS ?

### 🔵 **Sous Windows**

Windows aime mettre les fichiers partout, mais voici la bonne pratique :

📍 **Chemin recommandé** : `C:\Users\TON_UTILISATEUR\Documents\Python\`

```plaintext
C:\Users\TON_UTILISATEUR\Documents\Python\
```

✅ Avantages :  
✔️ Évite d’avoir du code éparpillé sur le bureau.  
✔️ Compatible avec les sauvegardes automatiques OneDrive (si activé).

⚠️ **Éviter** :  
❌ `C:\Python\` (trop générique, peut interférer avec les installations système).  
❌ `C:\Program Files\` (demande des droits admin inutiles).

---

### 🟢 **Sous Linux**

📍 **Chemin recommandé** : `~/Documents/Python/` ou `~/dev/python/`

```plaintext
/home/ton_utilisateur/Documents/Python/
```

✅ Avantages :  
✔️ Respecte la structure standard des dossiers utilisateur.  
✔️ Facile à gérer avec le terminal (`cd ~/Documents/Python/`).

⚠️ **Éviter** :  
❌ `/usr/bin/` ou `/opt/` (ces dossiers sont pour les programmes système, pas pour ton code).  
❌ Mettre ses scripts directement dans `~/` (ça devient vite le bazar).

---

### 🍏 **Sous macOS**

📍 **Chemin recommandé** : `~/Documents/Python/` ou `~/Developer/Python/`

```plaintext
/Users/ton_utilisateur/Documents/Python/
```

✅ Avantages :  
✔️ Aligné avec les conventions Mac.  
✔️ Compatible avec iCloud Drive si besoin.

⚠️ **Éviter** :  
❌ `/System/Library/` ou `/Applications/` (ne touche pas à ces dossiers).  
❌ Mettre ses scripts dans `~/Desktop/` (ton bureau ne doit pas être une décharge 🚮).

---

## 3. Comment exécuter un script proprement ?

Peu importe l'OS, une fois ton script organisé dans un bon dossier, exécute-le depuis le terminal :

```bash
cd ~/Documents/Python/projet1
python3 main.py
```

Si tu veux éviter de taper `python3`, crée un alias (Linux/macOS) ou modifie ton `PATH` sous Windows.

---

## 4. Conclusion

Peu importe ton OS, une bonne organisation de tes scripts Python te facilitera la vie. Prends l’habitude de structurer tes fichiers dès le début, ça évitera le chaos plus tard.

**Règle d’or :** un projet = un dossier. Un script indépendant = dans un dossier `scripts_utiles/`. Et surtout, évite de tout mettre sur ton bureau.

🛠️ Maintenant, organise tes fichiers et commence à coder proprement ! 🚀
