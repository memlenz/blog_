---
date: '2025-07-01T09:59:44+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: 'Installation Arch Linux : Guide accessible et complet'
description: "Un guide clair et accessible pour installer Arch Linux, inspiré de la documentation officielle, mais avec une vibe chill et pro."
categories: ["Linux", "Arch Linux", "Tutoriel"]
tags: ["Arch Linux", "Installation", "Linux", "Guide", "Terminal"]
series: ["Arch Linux"]
series_order: 0
---

# Installation Arch Linux

Linux, c’est un monde où tu peux littéralement choisir ce que tu veux devenir.  
Mais encore faut-il savoir ce que tu cherches.  

La communauté est vaste, il y a toujours une ressource quelque part.  
Alors pourquoi **Arch Linux** ?  

> [!WARNING]  
> Arch Linux, c’est le monde du **tout est possible**.  
> Tu veux un logiciel ? Tu l’as.  
> Si `pacman` ne suffit pas, `yay`, `paru` et toute la clique des AUR helpers sont là.  
> Bref : **TOUT EST POSSIBLE**.

Contrairement à d’autres distributions qui imposent des dépendances spécifiques, des binaires étranges ou du code à compiler, Arch suit un principe simple : **KISS (Keep It Simple, Stupid)**.  
C’est brut, mais puissant.

---

## Pré-requis

Avant de se lancer dans l’installation :  

- Savoir utiliser un **terminal** 👉 [Apprendre à utiliser le terminal](../terminal/)  
- Avoir une clé USB (≥ 2Go)  
- Une connexion Internet stable  
- Et surtout : **de la patience et un peu de café/thé** ☕

📖 Référence : [ArchWiki – Guide d’installation (Français)](https://wiki.archlinux.org/title/Installation_guide_(Fran%C3%A7ais))

---

## Étapes de l’installation

### 1. Télécharger l’ISO Arch Linux

👉 [Télécharger l’image ISO officielle](https://archlinux.org/download/)  
Grave-la sur ta clé USB avec `dd`, `balenaEtcher` ou `Rufus`.  

> Sous Linux :  

```bash
sudo dd if=archlinux.iso of=/dev/sdX bs=4M status=progress && sync
````

---

### 2. Booter sur le live USB

Redémarre ton PC et sélectionne ta clé USB dans le menu de boot.
Si tu vois un terminal avec le logo Arch → tu es prêt 🎉

---

### 3. Connexion Internet

Teste ta connexion avec :

```bash
ping archlinux.org
```

👉 En cas de souci WiFi → [Configurer le WiFi en ligne de commande](../wifi/)

---

### 4. Partitionner le disque

C’est l’étape la plus sensible. Tu peux utiliser :

- `fdisk` ou `cfdisk` (manuel)
- ou un guide 👉 [Comprendre les partitions Linux](../../partitions/)

---

### 5. Monter les partitions

Une fois créées :

```bash
mount /dev/sdXn /mnt
```

⚡ On prépare le terrain pour l’installation.

---

### 6. Installer le système de base

Avec `pacstrap` :

```bash
pacstrap /mnt base linux linux-firmware vim
```

---

### 7. Configurer le système

- Fstab
- Chroot
- Timezone
- Locales
- Utilisateur et mot de passe
  👉 On détaillera ça dans un sous-article dédié : [Configuration de base après installation](../config-base/)

---

### 8. Installer un bootloader

Grub ou systemd-boot ?
👉 [Choisir et installer son bootloader](./bootloader.md)

---

### 9. Rebooter 🎉

Un petit :

```bash
umount -R /mnt
reboot
```

Et normalement, tu arrives sur ton Arch fraîchement installée 🚀

---

## Ce qui vient après

Installer Arch, c’est juste la **fondation**.
Après ça :

- Configurer son environnement de bureau 👉 [Choisir et installer un DE/WM](./desktop-environnements.md)
- Installer des outils pour coder 👉 [Configurer Arch Linux pour le dev](./arch-dev-setup.md)
- Optimiser et personnaliser 👉 [Tweaks et astuces Arch](./arch-tweaks.md)

---

## Conclusion

Installer Arch Linux, c’est comme construire ta propre voiture avec chaque pièce choisie à la main.
Ça peut sembler dur, mais c’est ce qui fait que **ton système est vraiment le tien**.

---

## Liens utiles

- 📖 [ArchWiki – Installation guide](https://wiki.archlinux.org/title/Installation_guide_%28Fran%C3%A7ais%29)
- 🛠️ [Apprendre à utiliser le terminal](./terminal.md)
- 🖥️ [Comprendre les partitions Linux](./partitions.md)
- ⚡ [Configurer son environnement de bureau](./desktop-environnements.md)
