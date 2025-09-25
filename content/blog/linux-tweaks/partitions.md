---
title: "Partitions sous Linux : du simple au complexe"
date: '2025-07-30T09:59:44+01:00'
draft: false
tags: ["linux", "partition", "mbr", "gpt", "uefi", "legacy", "btrfs", "ext4", "installation"]
categories: ["linux-basics"]
series: ["Linux Essentials"]
series_order: 0
---

# Partitions sous Linux : du simple au complexe

Quand tu installes Linux, l’étape des **partitions** peut paraître mystique.  
Tu tombes sur des mots comme `boot`, `swap`, `ext4`, `btrfs`, `GPT`, `MBR`… et là, tu te dis : *ok, je suis perdu*.  

Respire. On va poser les bases, puis explorer les possibilités. L’idée, c’est pas de tout retenir d’un coup, mais d’avoir une **vue d’ensemble** pour comprendre ce que tu fais quand tu installes un système.

---

## Les bases : qu’est-ce qu’une partition ?

Un disque dur, c’est comme une grande maison 🏠.  
Une **partition**, c’est une séparation de cette maison en plusieurs appartements.  
Chaque partition a son rôle, son locataire : système, fichiers persos, mémoire virtuelle, etc.  

---

## Les partitions minimales pour démarrer Linux

Si tu veux juste installer et utiliser Linux sans te prendre la tête, un schéma **minimaliste** suffit :  

```

+-------------------+------------------+-----------------------------+
|       /boot       |       swap       |             /               |
|   (512 Mo - 1 Go) | (taille variable)| (le reste du disque, ext4) |
+-------------------+------------------+-----------------------------+

```

- **/boot** → contient le noyau et les fichiers nécessaires au démarrage.  
- **swap** → sert de mémoire de secours quand la RAM est saturée.  
- **/** (root) → contient tout le reste du système. Généralement en **ext4** (simple et fiable).  

---

## MBR vs GPT : organiser le disque

- **MBR (Master Boot Record)**  
  ➝ Ancien format, limité à 4 partitions principales et 2 To de disque. Fonctionne avec les systèmes en **Legacy BIOS**.  

- **GPT (GUID Partition Table)**  
  ➝ Format moderne, supporte presque un nombre illimité de partitions, disques énormes. Indispensable pour **UEFI**.  

👉 En gros :  

- Vieux PC → **Legacy + MBR**.  
- PC récent → **UEFI + GPT**.  

---

## Legacy vs UEFI : modes de démarrage

- **Legacy BIOS** : vieux système, simple, robuste, mais limité.  
- **UEFI** : moderne, plus rapide, permet un vrai support des disques GPT et nécessite une partition spéciale :  

```

+-------------------+
| EFI System (ESP)  |
| ~512 Mo FAT32     |
| montée sur /boot/efi |
+-------------------+

```

---

## Aller plus loin : partitionner comme un pro

Une fois que tu veux un peu plus de **contrôle**, tu peux séparer certaines parties du système pour des raisons de sécurité, performance ou maintenance.

Exemples classiques :  

```

+-------------------+   +------------------+   +-------------------+
|       /boot       |   |       swap       |   |        /          |
+-------------------+   +------------------+-----------------------+
|       /home       |
+-------------------+
|       /var        |
+-------------------+
|       /tmp        |
+-------------------+

```

- **/home** → tes fichiers perso séparés (pratique si tu réinstalles le système sans perdre tes données).  
- **/var** → logs, bases de données, fichiers qui changent souvent.  
- **/tmp** → fichiers temporaires, mieux isolés.  
- **/srv** → pour les serveurs, stocke les données des services (sites web, partages…).  

---

## Les systèmes de fichiers (FS)

Le **système de fichiers** (FS), c’est la manière dont tes données sont organisées dans une partition. Quelques grands classiques :  

- **ext4** → le standard, simple, fiable.  
- **XFS** → très performant pour les gros fichiers (souvent utilisé sur serveurs).  
- **Btrfs** → moderne, prend en charge les snapshots (sauvegardes instantanées), la compression, le RAID logiciel.  
- **ZFS** → encore plus avancé (snapshots, intégrité des données, scalabilité), mais plus complexe et pas toujours dispo par défaut.  

👉 Pour un usage quotidien :  

- ext4 = safe & simple.  
- Btrfs = cool si tu veux des snapshots et tester des fonctionnalités modernes.  

---

## Exemples pratiques

### Cas 1 : installation simple (UEFI + GPT)

```

1. 512 Mo  → EFI (FAT32, montée sur /boot/efi)
2. 2 Go    → swap
3. reste   → / (ext4)

```

### Cas 2 : installation avancée (serveur ou usage perso)

```

1. 512 Mo  → EFI
2. 2 Go    → swap
3. 30 Go   → / (ext4 ou btrfs)
4. 100 Go  → /home
5. 20 Go   → /var
6. reste   → /srv ou stockage

```

### Cas 3 : configuration Btrfs

Avec Btrfs, tu peux créer une seule partition et y définir des **sous-volumes** :  

```

+-------------------------------------------------------+
|                    Partition Btrfs                    |
|  - @      → /                                         |
|  - @home  → /home                                     |
|  - @var   → /var                                      |
|  - @snap  → snapshots du système                      |
+-------------------------------------------------------+

```

Ça simplifie la vie et rend les sauvegardes/rollbacks ultra simples.  

---

## Ressources utiles

- 🎥 [Learn Linux TV – Disk Partitioning](https://www.youtube.com/watch?v=2Qh5dYVRfww)  
- 📖 [Arch Wiki – Partitioning](https://wiki.archlinux.org/title/Partitioning)  
- 📘 [OpenClassrooms – Introduction à Linux (terminal et installation)](https://openclassrooms.com/fr/courses/7170496-apprenez-a-utiliser-le-terminal-linux)  
- 📚 [Btrfs Wiki](https://btrfs.wiki.kernel.org/index.php/Main_Page)  

---

## Conclusion

Le partitionnement, c’est pas une recette unique : ça dépend de ton matos, de ton usage et de ce que tu veux faire.  

- **Débutant** → reste simple : `/boot`, `swap`, `/` en ext4.  
- **Avancé** → explore Btrfs, sépare `/home`, `/var`, `/srv`.  
- **Serveur** → adapte selon les besoins (sécurité, logs, performances).  

Et rappelle-toi : même si ça semble complexe au début, chaque install est une occasion d’apprendre un peu plus. 😉
