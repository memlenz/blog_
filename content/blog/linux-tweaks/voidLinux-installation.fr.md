---
date: "2025-03-30T01:48:30+01:00"
title: "Bienvenue dans le Void : Installer Void Linux pas à pas"
draft: false
author: "Ayédoun Châ-Fine ADEBI"
description: "Un guide d'installation simple et efficace pour Void Linux, de la clé USB à votre premier boot."
categories: ["Blog Linux"]
tags: [Void Linux, Installation, Linux, Minimalisme]
---

## 🖤 **Bienvenue dans le Void !**

Ce tutoriel va te guider **pas à pas** dans l’installation de Void Linux, une distribution **légère et flexible** qui te donne un **contrôle total** sur ton système. Prêt à relever le défi ? 🚀

---

## 🎯 **Pourquoi Void Linux ?**

- **XBPS** : Un gestionnaire de paquets unique, rapide et efficace.
- **Runit** : Un système d'init ultra-léger pour des démarrages rapides.
- **Minimalisme** : Pas de logiciels superflus, juste ce dont tu as besoin.

---

## 🛠️ **Prérequis**

- Un PC 64 bits.
- Une clé USB (4 Go minimum).
- Une connexion Internet fiable.
- Un esprit curieux et aventureux. 😎

---

## 🌟 **Étape 1 : Télécharger l’ISO de Void Linux**

1. Rendez-vous sur [Void Linux Downloads](https://voidlinux.org/download/).
2. Choisis la version **Base Live ISO** pour ton architecture (généralement `x86_64`).

> **Astuce** : Si tu es incertain, opte pour la version `x86_64`.

---

## 💾 **Étape 2 : Créer une clé USB bootable**

1. Utilise **Etcher**, **Rufus**, ou la ligne de commande :
   ```bash
   sudo dd if=void-live-x86_64-*.iso of=/dev/sdX bs=4M status=progress
   ```
2. Remplace `/dev/sdX` par le nom de ta clé USB.

> **Attention** : `dd` n'a pas de bouton "annuler" ! Vérifie bien avant d'exécuter. 😱

---

## 🚀 **Étape 3 : Démarrer sur Void Linux**

1. Insère ta clé USB et redémarre ton PC.
2. Accède au BIOS/UEFI et choisis de démarrer sur la clé USB.
3. Sélectionne l’option `Void Linux` dans le menu de démarrage.

---

## 🖥️ **Étape 4 : Partitionner le disque**

1. Lance `cfdisk` :
   ```bash
   cfdisk /dev/sdX
   ```
2. Exemple de partitionnement :
   - 1 Go pour `/boot` (EFI si besoin).
   - Espace swap (optionnel, 2 Go+).
   - Reste pour `/`.
3. Formate les partitions :
   ```bash
   mkfs.ext4 /dev/sdX1  # Partition principale
   mkfs.vfat -F 32 /dev/sdX2  # Pour EFI
   mkswap /dev/sdX3  # Si swap
   ```

---

## 📦 **Étape 5 : Installer Void Linux**

1. Monte tes partitions :
   ```bash
   mount /dev/sdX1 /mnt
   mkdir -p /mnt/boot/efi
   mount /dev/sdX2 /mnt/boot/efi
   swapon /dev/sdX3
   ```
2. Lance l’installeur :
   ```bash
   void-installer
   ```
3. Suis les instructions pour configurer :
   - Disposition du clavier.
   - Configuration réseau.
   - Nom d'hôte et création d'utilisateur.
   - Système de fichiers.

---

## ⚙️ **Étape 6 : Installer le bootloader**

- Choisis **GRUB** pendant l'installation.
- Exécute ensuite :
  ```bash
  grub-install --target=x86_64-efi --efi-directory=/mnt/boot/efi --bootloader-id=void_grub
  grub-mkconfig -o /mnt/boot/grub/grub.cfg
  ```

---

## 🎉 **Étape 7 : Redémarrer et profiter**

1. Quitte l’installateur et démonte les partitions :
   ```bash
   umount -R /mnt
   reboot
   ```
2. Retire ta clé USB pendant le redémarrage.

Bienvenue dans le Void ! 🌌

---

## 🤓 **Astuces post-installation**

- Mets à jour ton système :
  ```bash
  sudo xbps-install -Syu
  ```
- Installe les outils de base :
  ```bash
  sudo xbps-install -S vim git base-devel
  ```
- Expérimente et personnalise ton environnement (WM, dotfiles, etc.).

---

## 📚 **Ressources utiles**

- [Void Linux Handbook](https://docs.voidlinux.org/)
- [Forum Void Linux](https://voidlinux.org/forums/)

Si tu rencontres un souci, n’hésite pas à demander de l’aide ou partager ton expérience ! 🎩
