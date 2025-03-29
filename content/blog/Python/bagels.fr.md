---
date: "2025-03-26T21:29:56+01:00"
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: "📝 Bagels : Un jeu de déduction logique en python"
description: "Découvrez comment implémenter Bagels, un jeu de puzzle mathématique inspiré de Mastermind, en Python. Tutoriel pas-à-pas avec gestion des indices (Pico/Fermi/Bagels) et code optimisé."
categories: ["TP Python"]
---

# 🎮 Bagels – A Logic Game in Python

Hey everyone! Today, I’m sharing a fun little Python project: **Bagels**, a deductive logic game. 🧠💡

The goal? **Guess a secret 3-digit number within 10 attempts**.  
But instead of getting direct hints, you receive **clues** to help you figure out the correct number:

🟢 **Game Rules**:

- _Fermi_ → A digit is **correct and in the right place** ✅
- _Pico_ → A digit is **correct but in the wrong place** 🔄
- _Bagels_ → No correct digits ❌

Example:  
If the secret number is **"123"** and you enter **"132"**, you’ll see:  
`Fermi Pico Pico` (1 is correct and in the right place, while 3 and 2 are correct but misplaced).

---

## **🚀 Source Code**

Here’s the full implementation in Python:

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

"""
    Nom du fichier : bagels.py
    Description : Un jeu de déduction logique pour
    deviner un nombre secret à trois chiffres.
    Vous avez 10 chances pour deviner le nombre.
    - Pico -> Un chiffre correct, mauvaise position.
    - Fermi -> Un chiffre correct, bonne position.
    - Bagels -> Aucun chiffre correct.

    Auteur : ADEBI Ayedoun Châ-Fine achafine@gmail.com
    Date : 03/16/2025
"""

import random

# Constante
GUESSES = 10  # NOMBRE DE CHANCES
DIGIT_LEN = 3  # NOMBRE DE CHIFFRES DU NOMBRE
MENU = """
    Bagels, a deductive logic game.
    By ADEBI Ayedoun Châ-Fine achafine@gmail.com

    Je suis en train de penser à un nombre à 3 chiffres.
    Essais de deviner lequel.
    Voici quelques indices :
    Quand je dis:       Voici ce à quoi je pense:
        Pico            Un chiffre est correct mais à la mauvaise position
        Fermi           Un chiffre est correct et à la bonne position
        Bagels          Aucun des chiffres n'est correct
    Vous avez 10 essais :
"""


def generer_nombre_secret():
    """ Générer un nombre secret unique à trois chiffres
    sous forme de liste.
    """
    chiffres = list(range(1, 10))
    random.shuffle(chiffres)
    return [str(chiffres[i]) for i in range(DIGIT_LEN)]


def obtenir_indices(input_list, guess_number):
    """Comparer l'entrée utilisateur avec le nombre secret
    et retourne des indices.
    """
    result = []
    for i in range(len(input_list)):
        if input_list[i] == guess_number[i]:
            result.append("Fermi")
        elif input_list[i] in guess_number:
            result.append("Pico")
    return " ".join(result) if result else "Bagels"


def valide_saisie():
    """Gère l'entrée utilisateur, l'utilisateur doit entrer
    un nombre à trois chiffres"""
    while True:
        saisie = input("> ").strip()
        if len(saisie) == DIGIT_LEN and saisie.isdigit():
            return list(saisie)
        print("Entrée invalide, vous devez entrer un nombre à trois chiffres")


def main():
    """Boucle principale du jeu"""
    rejouer = ""
    while True:
        guess_number = generer_nombre_secret()
        for i in range(GUESSES):
            print("Devine #", i+1)
            input_nbre = valide_saisie()
            if input_nbre == guess_number:
                print("Vous l'avez trouvé")
                break
            else:
                print(obtenir_indices(input_nbre, guess_number))
        else:
            print("Game Over!")
        print("Voulez-vous encore jouer ?? (oui ou non)")
        while True:
            rejouer = input("> ").strip().lower()
            if rejouer in ["oui", "non"]:
                break
            else:
                print("Vous devez répondre par 'oui' ou 'non' ")
        if rejouer == "non":
            print("Merci d'avoir joué")
            break


if __name__ == "__main__":
    print(MENU)
    main()
```

---

## **🔍 Code Breakdown**

- The program generates a **random 3-digit secret number**.
- The user enters a **guess** and receives a **clue** in return.
- The game loops for **up to 10 attempts** or until the player finds the correct number.
- At the end, the player can **choose to replay** or exit the game.

---

## **📌 How Can We Improve It?**

I have a few ideas, but I’d love to hear your suggestions!  
For example:

- Add a **hard mode** where the secret number has **no repeated digits**.
- Create a **graphical version** using Tkinter or Pygame.
- Implement a **multiplayer mode**, where Player 1 sets a number and Player 2 tries to guess it.

What do you think? Any other improvements you'd suggest? 🚀

💬 **Let me know in the comments if you tried the game or have any optimizations to propose!**

---

📌 **Follow me for more Python and development content!**  
👉 [[Dev.to](https://dev.to/memlenz) / [GitHub](https://github.com/memlenz) / [Twitter Profile](https://twitter.com/achafine)]
