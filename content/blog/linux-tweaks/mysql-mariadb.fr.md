---
title: "Installer MariaDB sur Arch Linux, Void Linux, et Debian/Ubuntu"
date: 2025-04-16
description: "Tutoriel étape par étape pour installer et configurer MariaDB (fork libre de MySQL) sur Arch Linux."
tags: ["mariadb", "mysql", "linux tweaks", "database", "tutoriel"]
categories: ["linux", "devops", "base de données"]
draft: false
---

## Pourquoi choisir MariaDB au lieu de MySQL ?

MariaDB est un **fork open source de MySQL** initié par les développeurs originaux de MySQL. Il a été créé en réponse aux inquiétudes concernant le rachat de MySQL par Oracle.

### ✅ Pourquoi préférer MariaDB :
- **100% libre et communautaire** — Maintenu par la communauté et la fondation MariaDB.
- **Compatible avec MySQL** — Même syntaxe SQL, mêmes clients, migration simple.
- **Performances solides** et mises à jour fréquentes.
- **Utilisé par Arch Linux par défaut** au lieu de MySQL.

> En résumé : pour les développeurs open source et les utilisateurs Arch Linux, **MariaDB est le choix naturel**.

---

## 🔧 Étapes d'installation de MariaDB

### 1. 📦 Installation du paquet

```bash
sudo pacman -S mariadb # arch linux
sudo xbps-install -S mariadb # void linux
sudo apt install mariadb # debian/ubuntu
```

---

### 2. 🛠️ Initialiser la base de données

```bash
sudo mariadb-install-db --user=mysql --basedir=/usr --datadir=/var/lib/mysql
```

Cette commande crée les fichiers nécessaires pour que le serveur fonctionne.

---

### 3. 🚀 Activer et démarrer le service MariaDB

```bash
sudo systemctl enable --now mariadb # arch-linux/debian/ubuntu
sudo ln -s /etc/sv/mariadb /var/service/ # void linux
```

> `enable` le démarre automatiquement au boot, `--now` le démarre immédiatement.

---

### 4. 🔐 Sécuriser l'installation avec `mariadb-secure-installation`

Lance la commande suivante :

```bash
sudo mariadb-secure-installation
```

Voici les réponses recommandées :

| Question | Réponse recommandée | Explication |
|---------|----------------------|-------------|
| Enter current password for root | Entrée (vide) | Aucun mot de passe par défaut |
| Switch to unix_socket authentication? | `n` | Permet l'accès avec mot de passe (plus pratique pour le dev) |
| Set root password? | `y` | Défini un mot de passe root |
| Remove anonymous users? | `y` | Supprime les utilisateurs sans identifiants |
| Disallow root login remotely? | `y` | Désactive les connexions root distantes (sécurité) |
| Remove test database and access to it? | `y` | Supprime la base de test par défaut |
| Reload privilege tables now? | `y` | Applique tous les changements |

---

## ✅ Tester la connexion

```bash
mariadb -u root -p
```

Entre ton mot de passe root défini précédemment.

---

## 🧰 Bonus : créer un utilisateur et une base

```sql
CREATE DATABASE nom_de_ta_base;
CREATE USER 'nom_utilisateur'@'localhost' IDENTIFIED BY 'motdepasse';
GRANT ALL PRIVILEGES ON nom_de_ta_base.* TO 'nom_utilisateur'@'localhost';
FLUSH PRIVILEGES;
```

---

## 🎉 Conclusion

Tu as maintenant une base de données MariaDB propre, sécurisée et prête à l’emploi sur Arch Linux.  
MariaDB offre une alternative open source puissante à MySQL, sans compromis sur la compatibilité ni la performance.

> Besoin d’un outil graphique ? Essaie `dbeaver` ou `mysql-workbench`.

---
