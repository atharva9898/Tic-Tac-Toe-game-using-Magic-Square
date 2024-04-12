# Tic-Tac-Toe-game-using-Magic-Square


This repository contains a Python implementation of a Tic-Tac-Toe game where the AI opponent uses the minimax algorithm with a magic square heuristic to make intelligent moves.

**How the Code Works**

The game is played on a 3x3 board between two players: "X" (AI) and "O" (human). The human player makes moves by specifying the row and column (1-3) on the board. The AI player uses the minimax algorithm to evaluate all possible future states of the game and choose the move that maximizes its chances of winning and minimizes the human player's chances.

The minimax algorithm leverages a magic square heuristic. A magic square is a grid where the sum of each row, column, and diagonal is equal. In this game, the AI assigns values to each cell in the board based on the magic square. It prioritizes moves that lead to higher scores based on these values.

The game continues until one player achieves three in a row (horizontally, vertically, or diagonally) or the board is full (a draw).

**Features:**

* Implements a basic Tic-Tac-Toe game with a human player ("O") and an AI opponent ("X").
* Uses the minimax algorithm with a magic square heuristic for the AI player.
* Displays the board after each move.
* Announces the winner or declares a draw.

**Getting Started**

1. Clone this repository.
2. Install any required dependencies using `pip install <package_name>`.
3. Run the game using `python main.py`.

**Example Gameplay**

```
 |  | 
-------
 |  | 
-------
 |  | 
Player X (AI) chooses row 1, column 1.
 |X|  | 
-------
 |  | 
-------
 |  | 
Enter row (1-3): 2
Enter column (1-3): 2
 |X|  | 
-------
 |O|  | 
-------
 |  | 
Player X (AI) chooses row 3, column 2.
 |X|  | 
-------
 |O|  | 
-------
 |X|  | 
... (game continues)

**Code Breakdown:**

* **`print_board(board)`:** This function takes the game board as input and displays it in a formatted way using row separators.

* **`initialize_board()`:** This function creates a new 3x3 board filled with empty spaces (" ") and returns it.

* **`check_win(board, player)`:** This function checks if a specific player ("X" or "O") has achieved victory by having three in a row (horizontally, vertically, or diagonally).

* **`is_draw(board)`:** This function checks if the game board is full (no empty spaces) which indicates a draw.

* **`get_empty_cells(board)`:** This function identifies all the empty cells (represented by " ") on the current game board and returns them as a list of tuples (row, column) coordinates.

* **` evaluate(board)`:** This function uses the magic square concept to evaluate the current game board state. It assigns values based on a pre-defined magic square (usually with a sum of 15) to each cell on the board. The function then calculates a score for the current player ("X") by summing the values of their occupied cells and subtracting the values of the opponent's ("O") occupied cells. 

* **` minimax(board, depth, is_maximizing)`:** This function implements the minimax algorithm for the AI player. It recursively explores all possible future moves (up to a certain depth) and evaluates the resulting board states using the `evaluate` function. The `is_maximizing` parameter indicates whether the current evaluation is for the AI ("X") trying to maximize its score or the human ("O") trying to minimize it. Based on this, the minimax algorithm chooses the move that leads to the best outcome for the AI.

* **`find_best_move(board)`:** This function utilizes the minimax algorithm to determine the optimal move for the AI player on the current board state. It iterates through all empty cells, simulates the AI placing its move there, and uses the minimax function to evaluate the resulting board. It then selects the move that leads to the highest score for the AI.

* **`main()`:** This function serves as the main entry point for the game. It initializes the board, sets the starting player ("X" - AI), and enters a game loop. The loop continues until the game ends (win or draw). Within the loop, the board is displayed, the AI makes its move using `find_best_move`, and then it prompts the human player for their move. The function validates the human player's input and updates the board accordingly. Finally, it checks for win or draw conditions and announces the result.


**Possible Enhancements:**

* **Difficulty Levels:** Implement difficulty levels by adjusting the depth of the minimax algorithm search. A higher depth allows the AI to explore more future possibilities but takes longer to compute.
* **Visual Enhancements:** Consider incorporating a graphical user interface (GUI) library like Tkinter or PyQt to create a more visually appealing game interface. 
* **Two-Player Mode:** Allow two human players to compete against each other by modifying the game loop to handle turns for both players. 
* **AI Evaluation Function:** Explore alternative evaluation functions beyond the magic square approach. These could involve analyzing potential winning formations or prioritizing moves that block the opponent's opportunities.

These enhancements can add complexity and features to your Tic-Tac-Toe game, making it more customizable and engaging for players.

