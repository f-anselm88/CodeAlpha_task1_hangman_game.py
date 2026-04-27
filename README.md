# 🎯 Hangman Game — CodeAlpha Python Internship

![Python](https://img.shields.io/badge/Python-3.8%2B-blue?style=flat-square&logo=python)
![Internship](https://img.shields.io/badge/Internship-CodeAlpha-purple?style=flat-square)
![Task](https://img.shields.io/badge/Task-1-orange?style=flat-square)
![Type](https://img.shields.io/badge/Type-Console%20Game-teal?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-lightgrey?style=flat-square)

> A console-based Hangman game built with Python that challenges the player to guess a hidden word letter by letter — with real-time visual feedback through a staged hangman rendering system.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Gameplay](#gameplay)
- [Technical Architecture](#technical-architecture)
- [Configuration](#configuration)
- [Concepts Demonstrated](#concepts-demonstrated)
- [Author](#author)

---

## Overview

This project was developed as **Task 1** of the **CodeAlpha Python Programming Internship**. It implements a fully interactive, console-based Hangman game where the player attempts to reveal a hidden word by guessing one letter at a time.

The game tracks guessed letters, counts incorrect attempts, and progressively renders a staged ASCII hangman figure as the player's chances diminish — delivering a complete game loop experience within the terminal.

---

## ✨ Features

- ✅ Random word selection from a curated word list
- ✅ Staged ASCII hangman visual (7 stages: 0–6)
- ✅ Real-time display of correctly guessed letters
- ✅ Tracking of incorrect guesses with a visible attempt counter
- ✅ Duplicate guess detection using Python `set` data structures
- ✅ Win/loss detection with end-game messages
- ✅ Clean separation of UI logic and game logic via functions

---

## 📁 Project Structure

```
Task1_hangman_game/
│
└── task1_hangman.py      # Main game module — all logic, UI, and configuration
```

---

## 🚀 Getting Started

### Prerequisites

- Python **3.8** or higher

### Installation

1. Clone the repository:

```bash
git clone https://github.com/f-anselm88/Task1_hangman_game.git
```

2. Navigate into the project directory:

```bash
cd Task1_hangman_game
```

3. Run the game:

```bash
python task1_hangman.py
```

No external dependencies required — built entirely on the Python standard library (`random`).

---

## 🕹️ Gameplay

At the start of each session, the program randomly selects a word and presents the player with blank placeholders. The player guesses one letter per turn.

```
 -----
 |   |
 |   O
 |  /|\
 |  / \
 |
===

Word:  _ _ _ _ _ _ _ _

Incorrect guesses (3/6): a, t, r
Enter a letter: p
```

**Win condition:** All letters in the word are correctly guessed before the 6th incorrect attempt.

**Loss condition:** 6 incorrect guesses are made — the hangman is fully drawn and the word is revealed.

---

## 🏗️ Technical Architecture

### Core Functions

| Function | Responsibility |
|---|---|
| `display_state(stage_index, word, guessed_letters, incorrect_letters)` | Renders the hangman stage, masked word, and incorrect guesses to the console |
| `get_player_guess(guessed_letters)` | Prompts and validates a single-letter input, preventing duplicate entries |
| `play_game()` | Orchestrates the full game loop — initialisation, turns, win/loss evaluation |

### Data Flow

```
play_game()
    │
    ├── Random word selected from WORD_LIST
    ├── guessed_letters (set) — tracks all guessed letters
    ├── incorrect_letters (set) — tracks wrong guesses
    │
    └── Loop until win or MAX_INCORRECT_GUESSES reached
            │
            ├── display_state() — renders current game state
            ├── get_player_guess() — validated user input
            └── Evaluate guess → update sets → check end condition
```

---

## ⚙️ Configuration

Game behaviour is controlled by three constants at the top of `task1_hangman.py`:

| Constant | Default Value | Description |
|---|---|---|
| `WORD_LIST` | `["developer", "detour", "function", "internship", "python"]` | Pool of words for random selection |
| `MAX_INCORRECT_GUESSES` | `6` | Maximum wrong guesses before game over |
| `HANGMAN_STAGES` | 7-element list (stages 0–6) | ASCII art frames for progressive hangman rendering |

To customise the game, simply modify these constants — no changes to the core logic are required.

---

## 🧠 Concepts Demonstrated

This project showcases the following Python programming fundamentals:

- **Functions** — modular design with clearly defined responsibilities per function
- **Loops** — `while` loop driving the main game cycle
- **Conditionals** — branching logic for guess evaluation and end-game detection
- **Sets** — efficient duplicate-guess prevention using Python's built-in `set` type
- **String manipulation** — masked word rendering with join and conditional expressions
- **Basic I/O** — `input()` and `print()` for interactive console communication
- **Randomisation** — `random` module for non-deterministic word selection

---

## 👤 Author

**Anselm Munango**
- GitHub: [@f-anselm88](https://github.com/f-anselm88)
- Programme: CodeAlpha Python Programming Internship

---

*Built as part of a structured internship programme to demonstrate core Python programming competencies through an interactive console application.*
