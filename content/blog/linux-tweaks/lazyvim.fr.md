---
date: "2025-03-30T01:32:00+01:00"
title: "De LazyVim à l'exécution de son premier script Python"
draft: false
author: "Ayédoun Châ-Fine ADEBI"
description: "Installer LazyVim, configurer les extras et les LSP pour coder en Python efficacement."
categories: ["Blog Python"]
tags: [Python, LazyVim, LSP, Neovim, Débutant]
---

## **1. Installer Neovim et Git**

LazyVim repose sur **Neovim**, donc on l’installe :

### **Pour Ubuntu/Debian :**

```sh
sudo apt update && sudo apt install -y neovim git
```

### **Pour Arch Linux :**

```sh
sudo pacman -S neovim git
```

### **Pour Void Linux :**

```sh
sudo xbps-install -S neovim git
```

Vérifie l’installation :

```sh
nvim --version
```

---

## **2. Installer LazyVim**

On clone LazyVim dans le dossier de config Neovim :
[Pour plus sur Lazyvim](https://www.lazyvim.org/)

```sh
git clone https://github.com/LazyVim/starter ~/.config/nvim
```

Ensuite, on lance Neovim :

```sh
nvim
```

LazyVim est prêt ! 🎉

---

## **3. Activer les Extras pour Python**

LazyVim propose des **extras** pour faciliter la config Python. Active `lang#python` en modifiant `~/.config/nvim/lua/config/lazy.lua` :

```lua
{
  "LazyVim/LazyVim",
  opts = {
    colorscheme = "tokyonight",
    extras = {
      "lang#python",
    },
  },
}
```

Recharge LazyVim avec :

```sh
nvim --headless "+Lazy! sync" +qa
```

---

## **4. Installer les outils pour Python**

Dans Neovim :

1. Ouvre Neovim : `nvim`
2. Appuie sur **Espace** pour ouvrir le menu.
3. Tape **c** pour "Code".
4. Tape **m** pour ouvrir Mason.
5. Appuie sur **Ctrl + f** et installe tape dans la barre python puis **entrer**, tu positionne le curseur devant ou sur chacun des éléments suivant et tu appuie **i** pour installer:
   - `python-lsp-server` (LSP Python)
   - `flake8` (Linting)
   - `black` (Formatage)
   - `autopep8` (Formatage alternatif)
   - `debugpy` (Debugging)
   - `ast-grep` (Recherche avancée)

---

## **5. Exécuter son premier script Python**

### **Créer un fichier Python**

Ouvre Neovim et crée un fichier `main.py` :

```sh
nvim main.py
```

Ajoute ce code :

```python
print("Hello, LazyVim!")
```

### **Exécuter le script depuis Neovim**

Tape :

```sh
!python3 main.py
```

Ou, mappe une touche pour exécuter plus vite :

```lua
vim.api.nvim_set_keymap("n", "<leader>r", ":w<CR>:!python3 %<CR>", { noremap = true, silent = true })
```

Maintenant, `Leader + r` (souvent `<Space>r`) exécute ton script en un clic.

---

## **Conclusion**

Tu es maintenant prêt à coder en Python sous Linux avec un environnement puissant ! **Tu peux maintenant explorer le développement Python avec un setup optimisé et léger.** 🚀
