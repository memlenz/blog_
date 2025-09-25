---
date: '2025-07-10T10:30:00+01:00'
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: "Prise en main du terminal Linux"
description: "Découvre les bases du terminal Linux avec OpenClassrooms et progresse vers des commandes avancées et astuces grâce à Learn Linux TV."
categories: ["Linux", "Arch Linux", "Terminal"]
tags: ["terminal", "ligne de commande", "bash", "zsh", "commandes Linux"]
series: ["Arch Linux"]
series_order: 1
---

# Prise en main du terminal Linux

Le terminal, c’est l’endroit où **la magie opère** sous Linux.  
Pas d’icônes, pas de clics interminables, juste un écran noir et un curseur qui t’attend.  

Ça peut impressionner au début, mais crois-moi : c’est le **super-pouvoir ultime** quand tu veux prendre le contrôle de ton système.  

---

## 1. Pourquoi apprendre le terminal ?

- C’est **universel** : les mêmes commandes marchent sur Arch, Debian, Ubuntu, Fedora…  
- C’est **rapide** : souvent plus rapide qu’une interface graphique.  
- C’est **puissant** : tu peux automatiser, enchaîner, combiner les commandes.  
- C’est **flexible** : tu construis ton propre workflow.  

👉 Bref, si tu veux vraiment comprendre Linux, **il faut passer par le terminal**.

---

## 2. Ressources pour bien démarrer

Avant de foncer dans les commandes, voici deux points d’entrée fiables :  

- 🎓 **OpenClassrooms** :  
  [Apprenez à utiliser la ligne de commande dans un terminal](https://openclassrooms.com/fr/courses/6173491-apprenez-a-utiliser-la-ligne-de-commande-dans-un-terminal)  
  → parfait pour les **bases** (naviguer dans les dossiers, créer des fichiers, comprendre la logique du shell).  

- 📺 **Learn Linux TV** :  
  [10 Linux Terminal Tips & Tricks](https://www.learnlinux.tv/10-linux-terminal-tips-and-tricks-to-enhance-your-workflow/)  
  → idéal pour les **astuces avancées** (alias, customisation du prompt, trucs pratiques).  

---

## 3. Les commandes de base à connaître

Voici un petit tableau des commandes incontournables :  

| Commande | Utilité |
|----------|---------|
| `ls` | Lister les fichiers et dossiers |
| `cd` | Changer de répertoire |
| `pwd` | Voir le chemin courant |
| `mkdir` | Créer un dossier |
| `touch` | Créer un fichier vide |
| `cp` | Copier fichiers/dossiers |
| `mv` | Déplacer ou renommer |
| `rm` | Supprimer |
| `cat` | Afficher le contenu d’un fichier |
| `less` | Lire un fichier page par page |
| `nano` / `vim` | Éditer un fichier |
| `man <commande>` | Lire le manuel d’une commande |
| `chmod` | Modifier les permissions |
| `chown` | Modifier le propriétaire |
| `grep` | Rechercher dans un fichier |
| `find` | Trouver un fichier |

💡 Astuce : tape `man ls` pour découvrir toutes les options de `ls`.  
Exemple :  

```bash
ls -lah
````

→ affiche les fichiers avec détails, permissions, taille et fichiers cachés.

---

## 4. Jouer avec les redirections et pipes

Le vrai pouvoir du terminal, c’est de **combiner** les commandes.

- **Redirection** :

```bash
ls > fichiers.txt
```

→ envoie la sortie de `ls` dans un fichier.

- **Pipes** :

```bash
ls -lah | grep ".txt"
```

→ envoie la sortie de `ls` dans `grep` pour chercher uniquement les fichiers `.txt`.

---

## 5. Niveau supérieur : alias, raccourcis et personnalisation

C’est là que **Learn Linux TV** devient intéressant. Quelques pépites :

- **Alias** (raccourcis pour commandes longues) :

```bash
alias ll="ls -la"
alias gs="git status"
```

Ajoute ça à ton `~/.bashrc` ou `~/.zshrc` pour les garder.

- **Prompt custom** (avec couleurs, utilisateur, répertoire) :
  Jay de Learn Linux TV montre comment personnaliser ton prompt pour qu’il t’affiche l’essentiel sans fouiller.

- **Commandes fun** :

```bash
curl wttr.in
```

→ affiche la météo directement dans ton terminal.

- **Cheatsheet instantanée** :

```bash
curl cheat.sh/grep
```

→ t’affiche un résumé des options de `grep`.

📺 Vidéo recommandée : [Learn Linux TV – Linux Command Line Full Tutorial](https://www.youtube.com/watch?v=avg65oY7sj4)

---

## 6. Pour aller encore plus loin

Une fois que tu maîtrises les bases, tu peux explorer :

- **Variables d’environnement** et `$PATH`
- **Scripts Bash** pour automatiser
- **Multiplexeurs** (`tmux`, `screen`) pour gérer plusieurs sessions dans un seul terminal
- **Gestion des processus** (`ps`, `top`, `kill`, `jobs`, `fg`, `bg`)
- **Cron jobs** et timers pour automatiser dans le temps

👉 Chacun de ces points pourra devenir un article dédié dans cette série.

---

## 7. Liens utiles

- 🎓 [OpenClassrooms – Apprenez à utiliser la ligne de commande](https://openclassrooms.com/fr/courses/6173491-apprenez-a-utiliser-la-ligne-de-commande-dans-un-terminal)
- 📺 [Learn Linux TV – 10 Terminal Tips & Tricks](https://www.learnlinux.tv/10-linux-terminal-tips-and-tricks-to-enhance-your-workflow/)
- 🎥 [Learn Linux TV – Linux Command Line Full Tutorial](https://www.youtube.com/watch?v=avg65oY7sj4)

---

## Conclusion

Le terminal, c’est ton passeport vers un Linux vraiment **libre et maîtrisé**.
Commence petit : naviguer, créer, supprimer des fichiers. Puis monte d’un cran : redirections, pipes, alias, scripts…

Avec un peu de pratique, tu verras qu’un simple écran noir devient ton **cockpit personnel**. 🚀
