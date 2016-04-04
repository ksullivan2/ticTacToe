# Unbeatable TicTacToe

### To play:
Open index.html in a browser.

## AI
The AI uses a recursive `minimax` algorithm to calculate the optimal move.

  1. For a given state, it generates a list of all possible moves.
  2. For each possible move, it then generates a new list of all the *opponent's* possible moves, and so on.
  3. At the bottom of the possibility tree, when the simulated game is finished, weights are assigned based on the outcome:
    * 10 points if the computer won
    * -10 points if the opponent won
    * 0 points for a tie
    * In addition, points are decremented based on how many levels deep in the recursion it is, essentially telling the computer that quicker wins are more valuable.
  4. As the recursive calls resolve, each level of the branch (therefore each possible move) is assigned a weight based on whose turn it was:
  	* The *maximum* of all possible scores of that branch if it was the computer's turn
  	* The *minimum* of all possible scores of that branch if it was the opponent's turn
  5. Finally, at the top level of the recursion, the computer chooses the move that had the highest possible score.
