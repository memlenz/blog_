---
title: "Installer PostgreSQL sur Arch, Void Linux et Debian/Ubuntu"
date: 2025-04-16
description: "Un guide complet pour installer, configurer et sécuriser PostgreSQL sur différentes distributions Linux."
tags: ["postgresql", "archlinux", "voidlinux", "debian", "ubuntu", "linux", "base de données"]
categories: ["linux", "devops", "base de données"]
draft: false
---

## 🐘 Pourquoi PostgreSQL ?

PostgreSQL est un **SGBD relationnel open source** puissant, robuste et très utilisé dans les environnements de production modernes. Il est apprécié pour :

- Sa **conformité aux standards SQL**
- Sa **gestion avancée des types de données**
- Son **système d’extensions** (comme `PostGIS`, `pg_trgm`, etc.)
- Sa **stabilité** et sa **communauté active**

---

# 🏗️ Installation par distribution

---

## 📦 Arch Linux

### 1. Installer PostgreSQL

```bash
sudo pacman -S postgresql
```

### 2. Initialiser la base

```bash
sudo -iu postgres initdb -D /var/lib/postgres/data
```

### 3. Activer et démarrer le service

```bash
sudo systemctl enable --now postgresql
```

### 4. Se connecter

```bash
sudo -iu postgres psql
```

---

## 📦 Void Linux

### 1. Installer PostgreSQL

```bash
sudo xbps-install -S postgresql
```

### 2. Initialiser la base

```bash
sudo -u postgres initdb -D /var/lib/postgresql/data
```

### 3. Activer avec runit

```bash
sudo ln -s /etc/sv/postgresql /var/service/
```

### 4. Vérifier que c’est actif

```bash
sv status postgresql
```

### 5. Se connecter

```bash
sudo -iu postgres psql
```

---

## 📦 Debian / Ubuntu

### 1. Installer PostgreSQL

```bash
sudo apt update
sudo apt install postgresql
```

> PostgreSQL est automatiquement initialisé et activé avec systemd.

### 2. Vérifier que le service est actif

```bash
sudo systemctl status postgresql
```

### 3. Se connecter

```bash
sudo -iu postgres psql
```

---

# 🔐 Sécurisation et utilisateur

Par défaut, PostgreSQL utilise **l’authentification "peer"** : seul l’utilisateur Unix `postgres` peut se connecter sans mot de passe.

Pour créer un utilisateur SQL avec mot de passe (et une base associée) :

```sql
-- connecté dans psql :
CREATE USER dev WITH PASSWORD 'motdepasse';
CREATE DATABASE projet OWNER dev;
GRANT ALL PRIVILEGES ON DATABASE projet TO dev;
```

> Tu peux ensuite te connecter avec :
```bash
psql -U dev -d projet -h localhost
```

---

# ⚙️ Configuration avancée (optionnelle)

- Fichier `pg_hba.conf` pour configurer les méthodes d’authentification
- Fichier `postgresql.conf` pour tuning (écoute réseau, journalisation, etc.)

Ces fichiers sont situés dans :
- `/var/lib/postgres/data/` (Arch)
- `/var/lib/postgresql/data/` (Void)
- `/etc/postgresql/*/main/` (Debian/Ubuntu)

---

## 🎉 Conclusion

PostgreSQL est désormais installé et prêt à l’emploi sur ta distro Linux préférée.  
Chaque distribution a ses petites particularités (init, services), mais la logique reste la même.

> Astuce : pense à installer `pgcli` pour une meilleure expérience en ligne de commande !

---
