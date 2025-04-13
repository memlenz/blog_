---
date: "2025-03-26T21:29:56+01:00"
draft: false
author: "Ayédoun Châ-Fine ADEBI"
title: "🎯 Implementing the Bagels Game in Python: A Deductive Logic Challenge"
description: "Learn how to code Bagels, a logic game inspired by Mastermind, in Python. A detailed tutorial explaining the gameplay, clue system (Pico/Fermi/Bagels), and code optimization."
categories: ["Python Projects", "Games and Algorithms"]
tags: ["Python", "Game", "Algorithms", "Logic"]
---

# 🎮 Bagels – A Logic Game in Python

Hey everyone! Today, I’m sharing a fun little Python project: **Bagels**, a deductive logic game. 🧠💡

The goal? **Guess a secret 3-digit number within 10 attempts**.  
But instead of direct hints, you receive **clues** to help you figure out the correct number:

🟢 **Game Rules**:

- _Fermi_ → A digit is **correct and in the correct position** ✅  
- _Pico_ → A digit is **correct but in the wrong position** 🔄  
- _Bagels_ → No correct digits ❌  

Example:  
If the secret number is **"123"** and you enter **"132"**, you’ll see:  
`Fermi Pico Pico` (1 is correct and in the right place, 3 and 2 are correct but misplaced).

---

## **🚀 Source Code**

Here’s the full implementation in Python:

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*-

"""
    File name: bagels.py
    Description: A deductive logic game where the player
    must guess a secret 3-digit number within 10 tries.
    - Pico -> One correct digit, wrong position.
    - Fermi -> One correct digit, right position.
    - Bagels -> No correct digits.

    Author: ADEBI Ayedoun Châ-Fine achafine@gmail.com
    Date: 03/16/2025
"""

import random

# Constants
GUESSES = 10  # NUMBER OF TRIES
DIGIT_LEN = 3  # LENGTH OF THE SECRET NUMBER
MENU = """
    Bagels, a deductive logic game.
    By ADEBI Ayedoun Châ-Fine achafine@gmail.com

    I am thinking of a 3-digit number.
    Try to guess what it is.
    Here are some clues:
    When I say:         That means:
        Pico            One digit is correct but in the wrong place
        Fermi           One digit is correct and in the right place
        Bagels          No digit is correct
    You have 10 attempts:
"""


def generate_secret_number():
    """Generate a unique 3-digit secret number
    as a list of digits.
    """
    digits = list(range(1, 10))
    random.shuffle(digits)
    return [str(digits[i]) for i in range(DIGIT_LEN)]


def get_clues(input_list, secret_number):
    """Compare user input to the secret number
    and return the appropriate clues.
    """
    result = []
    for i in range(len(input_list)):
        if input_list[i] == secret_number[i]:
            result.append("Fermi")
        elif input_list[i] in secret_number:
            result.append("Pico")
    return " ".join(result) if result else "Bagels"


def get_valid_input():
    """Handles user input; the player must enter
    a 3-digit number.
    """
    while True:
        guess = input("> ").strip()
        if len(guess) == DIGIT_LEN and guess.isdigit():
            return list(guess)
        print("Invalid input. Please enter a 3-digit number.")


def main():
    """Main game loop"""
    play_again = ""
    while True:
        secret_number = generate_secret_number()
        for i in range(GUESSES):
            print("Guess #", i + 1)
            user_guess = get_valid_input()
            if user_guess == secret_number:
                print("You got it!")
                break
            else:
                print(get_clues(user_guess, secret_number))
        else:
            print("Game Over!")
        print("Do you want to play again? (yes or no)")
        while True:
            play_again = input("> ").strip().lower()
            if play_again in ["yes", "no"]:
                break
            else:
                print("Please answer with 'yes' or 'no'")
        if play_again == "no":
            print("Thanks for playing!")
            break


if __name__ == "__main__":
    print(MENU)
    main()
```

---

## **🔍 Code Breakdown**

- The program generates a **random 3-digit secret number**.
- The user makes a **guess** and receives a **clue**.
- The game loops for **up to 10 tries**, or until the correct number is guessed.
- At the end, the player can **choose to replay** or quit.

---

## **📌 How Can We Improve It?**

I’ve got a few ideas, but I’d love to hear yours!  
For example:

- Add a **hard mode** where the secret number has **no repeating digits**.
- Create a **GUI version** using Tkinter or Pygame.
- Add a **multiplayer mode**, where Player 1 sets the number and Player 2 guesses.

What do you think? Got any other ideas to improve it? 🚀

💬 **Let me know in the comments if you tried the game or have optimizations to suggest!**

---

📌 **Follow me for more Python and dev content!**  
👉 [[Dev.to](https://dev.to/memlenz) / [GitHub](https://github.com/memlenz) / [Twitter Profile](https://twitter.com/achafine)]
