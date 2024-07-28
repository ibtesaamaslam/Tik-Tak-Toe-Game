# DEP

# Tic Tac Toe Game: Player vs Computer

This repository contains a simple implementation of the classic Tic Tac Toe game, where a human player can play against a computer that makes random moves. The game is played in the console, with the board displayed after each move.

## Features

- **Interactive Gameplay**: User inputs their move, and the board updates accordingly.
- **Random Computer Moves**: The computer selects moves randomly from available positions.
- **Win and Draw Checking**: The game checks for a winner or a draw after each move.
- **Console Output**: The game board and results are displayed in the console.

## How to Play

1. Clone the repository.
2. Run `tic_tac_toe.py` with Python.
3. Enter your move by selecting a number from 1 to 9.
4. The computer will make its move and the board will update.
5. The game continues until there is a winner or a draw.

## Game Board Layout

Positions are numbered as follows:

```
+---+---+---+
| 1 | 2 | 3 |
+---+---+---+
| 4 | 5 | 6 |
+---+---+---+
| 7 | 8 | 9 |
+---+---+---+
```

## Example Gameplay

```
Welcome to Tic Tac Toe
----------------------

+---+---+---+
| 1 | 2 | 3 |
+---+---+---+
| 4 | 5 | 6 |
+---+---+---+
| 7 | 8 | 9 |
+---+---+---+

Choose a number [1-9]: 5

+---+---+---+
| 1 | 2 | 3 |
+---+---+---+
| 4 | X | 6 |
+---+---+---+
| 7 | 8 | 9 |
+---+---+---+

Cpu choice:  3

+---+---+---+
| 1 | 2 | O |
+---+---+---+
| 4 | X | 6 |
+---+---+---+
| 7 | 8 | 9 |
+---+---+---+

Game over! Thank you for playing :)
```

## Requirements

- Python 3.x

## Running the Game

1. Open a terminal.
2. Navigate to the repository directory.
3. Run:
   ```sh
   python tic_tac_toe.py
   ```
