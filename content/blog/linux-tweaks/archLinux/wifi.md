---
date: '2025-07-20T11:15:00+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: "Configurer le WiFi sous Arch Linux"
description: "Un guide clair et accessible pour se connecter à un réseau WiFi sous Arch Linux, avec les commandes essentielles et des liens vers des ressources utiles."
categories: ["Linux", "Arch Linux", "Réseau"]
tags: ["wifi", "réseau", "Arch Linux", "iwctl", "wpa_supplicant", "internet"]
series: ["Arch Linux"]
series_order: 2
---

# Configurer le WiFi sous Arch Linux

Si tu installes Arch Linux sur un laptop, la **connexion WiFi** est souvent la première étape après avoir booté sur ta clé USB.  
Bonne nouvelle : c’est simple, mais faut savoir quelles commandes taper.  

---

## 1. Pré-requis

- Avoir un adaptateur WiFi fonctionnel (intégré ou USB).  
- Être dans le **live ISO Arch Linux** ou sur un système fraîchement installé.  
- Avoir un peu de patience (et peut-être un câble Ethernet de secours si ça galère 😅).  

---

## 2. Vérifier que le WiFi est détecté

Tape :  

```bash
ip link
````

Tu devrais voir une interface réseau de type `wlan0`, `wlp2s0` ou similaire.
Si tu ne vois rien → vérifie que ta carte est activée et que les pilotes sont présents.

👉 [Voir la doc ArchWiki sur le WiFi](https://wiki.archlinux.org/title/Wireless_network_configuration_%28Français%29)

---

## 3. Méthode 1 : Utiliser **iwd** (iwctl)

L’outil **iwd** est simple et recommandé.

Démarre l’outil interactif :

```bash
iwctl
```

Puis, dans le shell `iwctl` :

```bash
device list                # liste les périphériques WiFi
station wlan0 scan         # scanne les réseaux
station wlan0 get-networks # affiche les réseaux détectés
station wlan0 connect MonSSID
```

Tu peux tester la connexion avec :

```bash
ping archlinux.org
```

---

## 4. Méthode 2 : Utiliser **wpa_supplicant** (classique)

Si `iwd` n’est pas dispo, tu peux passer par `wpa_supplicant`.

Créer un fichier de configuration avec tes identifiants WiFi :

```bash
wpa_passphrase "MonSSID" "MonMotDePasse" > wpa.conf
```

Puis lancer :

```bash
wpa_supplicant -B -i wlan0 -c wpa.conf
dhcpcd wlan0
```

---

## 5. Persister la connexion après installation

Une fois Arch installée, tu peux installer un **Network Manager** pour gérer ton WiFi plus facilement :

- `networkmanager` (le plus utilisé, avec GUI si besoin)
- `connman`
- `wicd` (plus ancien)

Exemple avec NetworkManager :

```bash
sudo pacman -S networkmanager
sudo systemctl enable NetworkManager
sudo systemctl start NetworkManager
```

Ensuite, tu pourras utiliser :

```bash
nmcli device wifi connect MonSSID password MonMotDePasse
```

ou même installer une interface graphique si tu veux du confort.

---

## 6. Ressources utiles

- 📖 [ArchWiki – Wireless network configuration](https://wiki.archlinux.org/title/Wireless_network_configuration_%28Français%29)
- 🎓 [OpenClassrooms – Introduction aux réseaux informatiques](https://openclassrooms.com/fr/courses/7170496-initiez-vous-aux-reseaux-informatiques) (pour comprendre la base des réseaux)
- 📺 [Learn Linux TV – Networking Tips](https://www.learnlinux.tv/tag/networking/) (astuces avancées pour mieux gérer ses connexions)

---

## 7. Liens internes de la série

- 👉 [Prise en main du terminal](./terminal.md)
- 👉 [Installation Arch Linux – Guide complet](./installation-archlinux.md)
- 👉 [Comprendre les partitions Linux](./partitions.md)
- 👉 [Configuration de base après installation](./config-base.md)

---

## Conclusion

Configurer le WiFi sous Arch Linux, ce n’est pas sorcier :

- `iwctl` pour la méthode moderne et simple
- `wpa_supplicant` pour l’ancienne école
- `NetworkManager` pour le confort post-install

Une fois connecté, tout le reste de l’installation devient beaucoup plus fun 🚀
