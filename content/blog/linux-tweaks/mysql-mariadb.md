---
title: "Install Mysql (MariaDB) on Arch, Void Linux, and Debian/Ubuntu"
date: 2025-04-16
description: "Step-by-step tutorial to install and configure MariaDB (open-source fork of MySQL) on Arch Linux."
tags: ["mariadb", "mysql", "linux tweaks", "database", "tutorial"]
categories: ["linux", "devops", "database"]
draft: false
---

## Why Choose MariaDB Over MySQL?

MariaDB is an **open-source fork of MySQL**, created by the original MySQL developers. It was developed in response to concerns about Oracle acquiring MySQL.

### ✅ Why prefer MariaDB:
- **100% open-source and community-driven** — Maintained by the community and the MariaDB Foundation.
- **MySQL compatibility** — Same SQL syntax, same clients, easy migration.
- **Solid performance** and frequent updates.
- **Used by default on Arch Linux** instead of MySQL.

> In short, for open-source developers and Arch Linux users, **MariaDB is the natural choice**.

---

## 🔧 Installing MariaDB

### 1. 📦 Install the package

```bash
sudo pacman -S mariadb # Arch Linux
sudo xbps-install -S mariadb # Void Linux
sudo apt install mariadb # Debian/Ubuntu
```

---

### 2. 🛠️ Initialize the database

```bash
sudo mariadb-install-db --user=mysql --basedir=/usr --datadir=/var/lib/mysql
```

This command creates the necessary files for the server to run.

---

### 3. 🚀 Enable and start the MariaDB service

```bash
sudo systemctl enable --now mariadb # Arch Linux/Debian/Ubuntu
sudo ln -s /etc/sv/mariadb /var/service/ # Void Linux
```

> `enable` makes it start automatically on boot, `--now` starts it immediately.

---

### 4. 🔐 Secure the installation with `mariadb-secure-installation`

Run the following command:

```bash
sudo mariadb-secure-installation
```

Here are the recommended responses:

| Question | Recommended Answer | Explanation |
|---------|--------------------|-------------|
| Enter current password for root | Press Enter (leave blank) | No default password |
| Switch to unix_socket authentication? | `n` | Allows password-based access (more convenient for development) |
| Set root password? | `y` | Set a root password |
| Remove anonymous users? | `y` | Remove users without credentials |
| Disallow root login remotely? | `y` | Disable remote root login (security) |
| Remove test database and access to it? | `y` | Remove the default test database |
| Reload privilege tables now? | `y` | Apply all changes |

---

## ✅ Test the connection

```bash
mariadb -u root -p
```

Enter the root password you set earlier.

---

## 🧰 Bonus: Create a user and a database

```sql
CREATE DATABASE your_database_name;
CREATE USER 'your_username'@'localhost' IDENTIFIED BY 'your_password';
GRANT ALL PRIVILEGES ON your_database_name.* TO 'your_username'@'localhost';
FLUSH PRIVILEGES;
```

---

## 🎉 Conclusion

You now have a clean, secure, and fully functional MariaDB database installed on Arch Linux.  
MariaDB offers a powerful open-source alternative to MySQL without compromising on compatibility or performance.

> Need a graphical tool? Try `dbeaver` or `mysql-workbench`.

---
```

Let me know if you'd like additional content, such as tips for performance tuning or advanced MariaDB configuration!
