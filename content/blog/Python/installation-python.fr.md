---
title: "Installer Python sur Windows, Linux et Mac"
draft: false
author: "Ayédoun Châ-Fine ADEBI"
date: "2025-04-10T23:09:59+01:00"
description: "Un guide détaillé pour installer Python sur Windows, Linux et macOS, sans prise de tête."
categories: ["Blog Python"]
tags: [Python, Installation, Windows, Linux, Mac]
---

## Pourquoi installer Python ?

Avant de se lancer dans la programmation avec Python, il faut d'abord l'avoir sur sa machine. Contrairement à certains langages qui viennent déjà intégrés aux systèmes d’exploitation, Python doit être installé manuellement sur Windows, et parfois mis à jour sur Linux et macOS.

---

## Installer Python sur **Windows** 🖥️

Sur Windows, Python **n'est pas installé par défaut**. Voici comment l'obtenir :

### **1. Télécharger Python**

- Rendez-vous sur le site officiel : [python.org](https://www.python.org/downloads/).
- Prenez la **dernière version stable** (évitez les versions en bêta).
- Téléchargez l’installateur **Windows Installer (64-bit)**.

### **2. Lancer l’installation**

- **Cochez l’option "Add Python to PATH"** avant d’installer.  
  (C'est crucial pour pouvoir exécuter `python` dans le terminal sans galère.)
- Cliquez sur **"Install Now"** et laissez faire.

### **3. Vérifier l’installation**

- Ouvrez une invite de commande (`Win + R` → tapez `cmd` → Entrée).
- Tapez :

  ```sh
  python --version
  ```

  Si ça affiche une version comme `Python 3.x.x`, tout est bon ! 🎉

Si ça ne marche pas, **votre terminal ne trouve pas Python**. Dans ce cas, redémarrez votre PC ou ajoutez manuellement Python au `PATH`.

---

## Installer Python sur **Linux** 🐧

La plupart des distributions Linux viennent avec Python préinstallé. Pour vérifier :

```sh
python3 --version
```

Si Python n'est pas installé ou si vous voulez la dernière version :

### **Debian / Ubuntu**

```sh
sudo apt update && sudo apt install python3
```

### **Arch Linux**

```sh
sudo pacman -S python
```

### **Void Linux**

```sh
sudo xbps-install -S python3
```

Une fois installé, testez avec `python3 --version`.

---

## Installer Python sur **macOS** 🍏

Sur Mac, **Python est déjà installé**, mais souvent en version ancienne. Mieux vaut utiliser Homebrew pour une version à jour :

### **1. Installer Homebrew (si ce n'est pas fait)**

```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

### **2. Installer Python**

```sh
brew install python
```

Vérifiez ensuite avec :

```sh
python3 --version
```

---

## Conclusion 🏁

✅ **Windows** → Téléchargement manuel + "Add to PATH".  
✅ **Linux** → Vérifier puis installer via `apt`, `pacman` ou `xbps-install`.  
✅ **Mac** → Homebrew pour gérer les versions.

Si tout est bon, vous êtes prêt à coder ! 🚀
