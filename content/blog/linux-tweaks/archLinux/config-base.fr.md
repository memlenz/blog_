---
date: '2025-09-25T13:30:00+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: "Configuration de base après installation d'Arch Linux"
description: "Guide post-installation pour configurer un Arch Linux débutant-friendly : fstab, chroot, timezone, locales et plus."
categories: ["Linux", "Arch Linux", "Tutoriel"]
tags: ["Arch Linux", "Configuration", "Post-installation", "fstab", "chroot", "Timezone", "Locales"]
series: ["Arch Linux"]
series_order: 3
---

# Configuration de base après installation d'Arch Linux

Après avoir installé Arch Linux et redémarré depuis le live USB, ton système est minimal.  
Pour qu’il soit pleinement fonctionnel, il faut effectuer quelques **configurations de base**, comme monter les partitions, définir la timezone, configurer les locales et préparer le système pour ton utilisateur.

Pas de panique : on va le faire étape par étape, de façon **débutant-friendly**, avec explications et commandes claires.

---

## 1. Chrooter dans le système installé

Avant toute configuration, il faut accéder au système installé depuis le live USB :  

```bash
mount /dev/sdXn /mnt        # monter la partition racine
mount /dev/sdX1 /mnt/boot   # si /boot séparé
mount /dev/sdXn /mnt/home   # si /home séparé
arch-chroot /mnt
````

> `arch-chroot` te permet de travailler comme si tu étais déjà dans ton système installé.

📖 Réf : [ArchWiki – chroot](https://wiki.archlinux.org/title/Chroot)

---

## 2. Configurer fstab

`fstab` (File System Table) permet à Linux de **savoir quelles partitions monter automatiquement** au démarrage.

Génère un fichier automatiquement avec :

```bash
genfstab -U /mnt >> /mnt/etc/fstab
cat /mnt/etc/fstab   # vérifier
```

* `-U` → utilise les UUID pour identifier les partitions (recommandé)
* Vérifie toujours que les entrées sont correctes pour `/`, `/boot`, `/home` et `swap`.

📖 Réf : [ArchWiki – Fstab](https://wiki.archlinux.org/title/Fstab)

---

## 3. Définir la timezone

Renseigne ta timezone pour que l’heure du système soit correcte :

```bash
ln -sf /usr/share/zoneinfo/Europe/Paris /etc/localtime
hwclock --systohc
```

* `ln -sf` → crée un lien symbolique vers ta timezone
* `hwclock --systohc` → synchronise l’horloge matérielle avec l’heure système

📖 Réf : [ArchWiki – Time](https://wiki.archlinux.org/title/Time)

---

## 4. Configurer les locales

1. Éditer `/etc/locale.gen` et décommenter ta locale, par exemple :

```
en_US.UTF-8 UTF-8
fr_FR.UTF-8 UTF-8
```

2. Générer les locales :

```bash
locale-gen
```

3. Créer le fichier `/etc/locale.conf` :

```bash
echo "LANG=fr_FR.UTF-8" > /etc/locale.conf
```

📖 Réf : [ArchWiki – Locale](https://wiki.archlinux.org/title/Locale)

---

## 5. Définir le hostname et le hosts

Choisis un nom pour ton PC :

```bash
echo "monpc" > /etc/hostname
```

Puis ajoute dans `/etc/hosts` :

```
127.0.0.1   localhost
::1         localhost
127.0.1.1   monpc.localdomain monpc
```

---

## 6. Configurer la connexion réseau (optionnel post-live)

* Pour un réseau filaire : souvent plug-and-play avec systemd-networkd ou NetworkManager.
* Pour le WiFi, tu peux configurer via `iwctl` ou NetworkManager après reboot.
  👉 Voir : [Configurer le WiFi sous Arch Linux](../wifi/)

---

## 7. Installer un éditeur de texte pratique

```bash
pacman -S vim nano
```

Pour éditer les fichiers de configuration sans souci.

---

## 8. Créer un utilisateur normal

C’est important pour ne pas travailler tout le temps en root :

```bash
useradd -m -G wheel -s /bin/bash memlenz
passwd memlenz
pacman -S sudo
EDITOR=vim visudo
```

Dans `visudo`, décommente :

```
%wheel ALL=(ALL) ALL
```

Maintenant ton utilisateur peut utiliser `sudo`.

📖 Réf : [ArchWiki – Users and Groups](https://wiki.archlinux.org/title/Users_and_groups)

---

## 9. Installer le bootloader

Pour que ton système démarre correctement après reboot :

* GRUB pour BIOS/UEFI
* systemd-boot pour UEFI simple

👉 Voir : [Installer un bootloader](./bootloader.md)

---

## 10. Reboot et vérifier

```bash
exit       # quitter le chroot
umount -R /mnt
reboot
```

* Connecte-toi avec ton utilisateur normal
* Teste sudo, ping, et la configuration du terminal

---

## Liens utiles

* 📖 [ArchWiki – Installation guide](https://wiki.archlinux.org/title/Installation_guide_%28Fran%C3%A7ais%29)
* 🛠️ [ArchWiki – Fstab](https://wiki.archlinux.org/title/Fstab)
* ⏱️ [ArchWiki – Time](https://wiki.archlinux.org/title/Time)
* 🌐 [ArchWiki – Locale](https://wiki.archlinux.org/title/Locale)
* 👤 [ArchWiki – Users and Groups](https://wiki.archlinux.org/title/Users_and_groups)

---

## Conclusion

Ces étapes sont la **fondation de ton Arch Linux**.
Après ça, tu as :

* Un système stable avec partitions montées
* La timezone correcte
* Les locales configurées
* Ton utilisateur prêt à l’emploi
* Sudo fonctionnel pour les tâches administratives

Tout est prêt pour installer ton **environnement graphique** ou ton **WM**, et commencer à personnaliser ton Arch à ta vibe 🚀
