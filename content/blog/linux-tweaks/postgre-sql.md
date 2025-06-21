---
title: "Install PostgreSQL on Arch, Void Linux, and Debian/Ubuntu"
date: 2025-04-16
description: "A complete guide to installing, configuring, and securing PostgreSQL on various Linux distributions."
tags: ["postgresql", "archlinux", "voidlinux", "debian", "ubuntu", "linux", "database"]
categories: ["linux", "devops", "database"]
draft: false
---

## 🐘 Why PostgreSQL?

PostgreSQL is a **powerful open-source relational database system** used widely in modern production environments. It's known for:

- **Standards-compliance with SQL**
- **Advanced data type support**
- **Rich extension ecosystem** (e.g., `PostGIS`, `pg_trgm`)
- **Stability and active community**

---

# 🏗️ Installation by Distribution

---

## 📦 Arch Linux

### 1. Install PostgreSQL

```bash
sudo pacman -S postgresql
```

### 2. Initialize the data directory

```bash
sudo -iu postgres initdb -D /var/lib/postgres/data
```

### 3. Enable and start the service

```bash
sudo systemctl enable --now postgresql
```

### 4. Connect to PostgreSQL

```bash
sudo -iu postgres psql
```

---

## 📦 Void Linux

### 1. Install PostgreSQL

```bash
sudo xbps-install -S postgresql
```

### 2. Initialize the data directory

```bash
sudo -u postgres initdb -D /var/lib/postgresql/data
```

### 3. Enable the service with runit

```bash
sudo ln -s /etc/sv/postgresql /var/service/
```

### 4. Check if it's running

```bash
sv status postgresql
```

### 5. Connect to PostgreSQL

```bash
sudo -iu postgres psql
```

---

## 📦 Debian / Ubuntu

### 1. Install PostgreSQL

```bash
sudo apt update
sudo apt install postgresql
```

> PostgreSQL is automatically initialized and enabled with systemd.

### 2. Check the service status

```bash
sudo systemctl status postgresql
```

### 3. Connect to PostgreSQL

```bash
sudo -iu postgres psql
```

---

# 🔐 Security & User Setup

By default, PostgreSQL uses **peer authentication**: only the Unix `postgres` user can connect without a password.

To create a SQL user with a password and a database:

```sql
-- inside psql:
CREATE USER dev WITH PASSWORD 'yourpassword';
CREATE DATABASE project OWNER dev;
GRANT ALL PRIVILEGES ON DATABASE project TO dev;
```

> You can now connect using:
```bash
psql -U dev -d project -h localhost
```

---

# ⚙️ Optional Configuration

- `pg_hba.conf` to manage authentication methods
- `postgresql.conf` for tuning (listen addresses, logging, etc.)

These files are located in:
- `/var/lib/postgres/data/` (Arch)
- `/var/lib/postgresql/data/` (Void)
- `/etc/postgresql/*/main/` (Debian/Ubuntu)

---

## 🎉 Conclusion

PostgreSQL is now fully installed and running on your favorite Linux distribution.  
Each distro has its own quirks (init system, service handling), but the core setup remains consistent.

> Pro tip: install `pgcli` for an enhanced CLI experience!

---
