# Tic Tac Toe (CLI with AI)

A command-line Tic Tac Toe game where you can play against an AI opponent powered by the **Minimax algorithm**. The AI always makes the optimal move, making it impossible to beat (though you can still tie!).

---

## Features

* Play as **X** or **O** (X always goes first).
* Human vs AI gameplay in the terminal.
* AI opponent uses **Minimax with memoization** for optimal decision-making.
* Detects **win, loss, or draw**.
* Option to replay after each game.

---

## How to Run

```bash
python main.py
```

You’ll be asked to choose your symbol (**X** or **O**), then take turns placing marks on the 3×3 board.

---

## Example Gameplay

```
X or O? (X goes first)
>>> X

 1 | 2 | 3
---|---|---
 4 | 5 | 6
---|---|---
 7 | 8 | 9

Input number of square you'd like to move to:
>>> 5

AI chooses square 1
```

---

## Code Overview

* **disp class**
  Handles displaying the Tic Tac Toe board in the console.

* **pos class**

  * `checkWin(l)`: Checks if X or O has won, or if it’s a draw.
  * `openSpots(l)`: Returns available moves.
  * `closedSpots(l)`: Returns filled positions.

* **minimax class**
  Implements the **Minimax algorithm** with memoization:

  * `maxX(l)`: Maximizing function for player X.
  * `minO(l)`: Minimizing function for player O.
    Uses recursion to simulate all possible moves until terminal states (win, lose, draw).

* **Main loop**

  * Initializes board.
  * Asks player to pick symbol.
  * Alternates turns between player and AI until the game ends.
  * Offers to restart.

---

## The Minimax Algorithm (Simplified)

The AI considers **all possible future moves** recursively:

1. If a move leads to a **win**, it scores `+1` for X or `-1` for O.
2. If it leads to a **draw**, it scores `0`.
3. The AI chooses the **best score** depending on whether it’s minimizing (O) or maximizing (X).
4. Memoization (`transposeX`, `transposeO`) is used to avoid recomputing already-seen board states.

This ensures the AI **never makes a mistake**.

---

## Possible Improvements to be done in future.

* Add a GUI (e.g., Tkinter or Pygame).
