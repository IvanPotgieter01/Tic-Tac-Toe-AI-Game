# Tic-Tac-Toe-AI-Game
AI game implemented using the powerful Minimax search algorithm. The game, Tic Tac Toe, provides an engaging experience for players, with an intelligent AI opponent that utilizes the Minimax algorithm to make optimal moves.

## Background
Artificial Intelligence (AI) is growing at an exponential rate, both in popularity and complexity. In order for the concept of AI to be taught to students, a simple AI model is necessitated. This model will showcase the basic concepts of creating and training an AI bot. There exists a need for a basic AI game that demonstrates the uses a popular search algorithm. Such a game would be able to aid in future developments in AI, both in the gaming sector, as well as the field as a whole. Tic-Tac-Toe is a popular game that is simple enough to implement, yet complex enough to demonstrate the use of common AI algorithms like the minimax search algorithm. Due to the game’s popularity, it serves as a great example for learning. This is because the concept is simple and familiar to most. The Tic-Tac-Toe game can also be a fun and engaging way for people (especially students) to interact with and learn about AI. The game will be able to teach students about the concepts of AI, without being overly intimidating. 
Playing Tic-Tac-Toe against an AI player can also offer learning opportunities for players. By observing the AI player's moves, players can learn different strategies and techniques for playing the game. This can enable them to develop their own skills and approaches. This can play an important role in the brain development of young children. The Tic-Tac-Toe game can also serve as a platform for future developments in AI and game design. For example, the game can be used as a test bed for new AI algorithms or game theories. It can also help researchers and designers understand human decision-making processes in games. Researchers can use the algorithms used in Tic-Tac-Toe to build much more complex algorithms to solve complex problems.

![image](https://github.com/IvanPotgieter01/Tic-Tac-Toe-AI-Game/assets/109952133/427f1d9c-031f-48e8-970a-0e282d5b3186)

The AI will use the minimax search algorithm to search a tree of nodes (possible moves) in order to determine the best move to make to maximise its chances of winning the game. If the game has progressed to a point where the AI player can no longer win, it will attempt to prevent its opponent from winning and thereby drawing the game. This strategy perfectly falls in line with what the minimax search algorithm was designed to do. As shown in the figure below, each possible future game state is generated, for the current game state.  Alpha-beta pruning can be employed in order to speed up the search process. 
![image](https://github.com/IvanPotgieter01/Tic-Tac-Toe-AI-Game/assets/109952133/c3cca6cf-e0f4-4deb-b405-e2ffe33f0c31)


## Choice of Techniques
•	The board is represented as a list with 9 elements. Each element represents a cell on the board. Since the number of possible moves in Tic-Tac-Toe is quite small, it makes sense to represent each of the 9 blocks on the board as an element.

•	The board’s initial state is empty, with each cell containing a space character (“”). This falls in line with how the game would be played in real life on paper.

•	The X player is represented as a string “X”.

•	The O player is represented as a string “O”.

•	The AI player uses the minimax algorithm to determine its best move.

•	The minimax algorithm evaluates the board state by recursively examining all possible future moves and choosing the one that maximizes the AI player's chance of winning the game.

•	The evaluation function assigns a score to each board state (higher scores indicate a higher chance of winning for the AI player).

•	Once the best move is determined, the AI makes that move and waits for the player to make their next move.

## Search order and reason for techniques
The minimax algorithm is a popular recursive algorithm in the game development space. This is because the minimax algorithm takes the possible future moves of its opponent into account. Therefore, it is able to make the best possible move to optimize its chances of winning. The main goal of using the minimax algorithm is to maximize the AI’s chances of winning and minimize the opponent’s chances of winning. By being able to evaluate future states, the AI will be able to make the best possible move. Such a move being one that has the highest chance of resulting in a victory for the AI player. With an increase in game states (for example a larger playing grid), the AI will have an increasing advantage over its human opponent. In order to optimise the search, one approach is to use alpha-beta pruning. This will speed up the search process, as it will eliminate branches that are unlikely to lead to a favourable outcome. This can be seen below in Figure 4. By eliminating nodes to search, the search space is reduced and the search time is reduced. 
The search process for Tic-Tac-Toe happens as follows:
1.	The minimax algorithm creates a game tree that represents potential moves and game states. This includes X’s and O’s placed in different positions on the board.
2.	The AI recursively searches this tree, starting from the current state of the game and working its way down. The leaf nodes of the search tree represent the possible ending states for the game. 
3.	At each level of the tree, the AI alternates between maximizing and minimizing the score to simulate the possible future moves of the opponent.
4.	Alpha-beta pruning is used to eliminate unlikely branches, reducing the search space and thereby speeding up the search process. 
![image](https://github.com/IvanPotgieter01/Tic-Tac-Toe-AI-Game/assets/109952133/05e2f2e2-8e45-4ec9-8680-d23765446843)
The operators selected for a game-playing AI have a large impact on the complexity of the search space. This is why the selection of operators is crucial in developing an AI that performs well in a particular game. In games, both speed and accuracy play a cardinal role. Therefore, a balance needs to be achieved between these two important factors. In a relatively simple game such as a 3 × 3 grid Tic-Tac-Toe, there are only a finite number of moves that can be made. Therefore, the search space is quite narrow and the selection of operators is less crucial. However, in more complex games such as chess, the selection of operators can have a significant impact on the AI's performance. This is because there are an immense number of possible moves to consider and countless outcomes to evaluate. Therefore, choosing suitable operators will have a very large impact on the algorithm’s game-playing success. The operators in Tic-Tac-Toe are the placement of X's and O's on the 3 × 3 grid. These can be easily represented as strings in the game code.

## Description of program design
### Importing modules
•	The “pygame” module is imported as it is very useful for creating games. This module contains the functionality that is needed to create objects and display the graphics for the game.

•	The “time” module is also imported as it is useful for introducing “pauses” that are sometimes necessary between events in the game. 
Game initialisation

•	“pygame.init()” initializes all of the imported Pygame modules.

•	A window size of 300 × 300 pixels is established for the game window.

•	Colours are defined as RGB tuples. These provide the basic colours for the game window and text and the game.

•	“pygame.display.set_mode(WINDOW_SIZE)” creates the game window with the above specified dimensions.

•	The font object determines the font and size of the text that will be displayed in the game window.

•	The game variables are initialized: the “player” variable is set to "X" (the human player’s move).

•	At the start of the game, all cells on the board are set as empty (“”).
### Drawing the game board
•	“draw_board()” is a function that draws the 3 × 3 grid on the game window. This grid displays the moves of the players on it. The function uses a nested loop to traverse through each cell in the 3 × 3 grid and draw a black rectangle for each cell. “font.render” renders the text object for the current cell's value ("X", "O" or ""). 

•	Finally “screen.blit” draws the text objects on the game screen.
Checking if the game is over

•	“check_game_over()” is a function that checks if there is a winner or if the game is a tie. It checks all the possible winning combinations and returns the winner if one exists. Firstly, the function loops over all the rows in the board and checks if there is a row that contains all of the same values (“X’s” or “O’s”). Next, it does the same with the columns and finally with the diagonals. If all cells are filled, but there is no winner, it returns "Tie" as the game has ended in a draw.
### Determining the AI player’s move
•	“ai_turn()” is the function that allows the AI to make its move. It uses the minimax algorithm to determine the optimal move. The function starts by setting a “best_score” as negative infinity, “best_move_i” as -1 and “best_move_j” as -1. These values are placeholders and the actual values will be determined as the function progresses. 

•	“alpha” and “beta” are initialized for the Alpha-Beta pruning that will take place during the execution of the minimax search algorithm. “alpha is the best score (from the perspective of the maximizing player) that is guaranteed at that point in the branch. “beta” is the best score (from the perspective of the minimizing player) that is guaranteed at that point in the branch. Alpha’s initial value is negative infinity, while beta’s initial value is positive infinity. 

•	The variable “best_score” is used to track the highest score from these simulated moves. The function iterates through each cell on the board. When an empty cell is reached, the AI calls the “minimax()” function in order to determine the score of a move made in that specific cell. If this score is higher than the current “best_score”, this becomes the new “best_score”. This process continues until each empty cell has been evaluated. Thereafter, the AI will make the move with the highest score associated with it. This will be the “best” move that the AI can make in order to optimise its chances of winning the game.
### The Minimax search algorithm
•	The “minimax()” function is the heart of the AI's decision-making process. It is a recursive function that simulates all the possible moves that the AI can make in the game. The function rates each of these moves. Based on these ratings, it determines the best move to make. The AI "thinks" ahead and predicts the moves that the human player will make in order to determine its next move after that.

•	The first thing the function does is to check the current state of the game by calling the “check_game_over()” function. If the game is a tie, it will return a 0. If the human player (“X”) has won, it will return -1 and if the AI (“O”) won, it will return 1.

•	If the player is the maximizing player (the AI) the boolean “isMax” is true and the “best_score” will be initialized to a very low value (arbitrarily negative infinity in this case). Next, the function iterates through the game board. If an empty cell is reached, the function will place an “O” in it. Next, it recursively calls the “minimax()” function with an increased depth and it switches to the minimizing player (the human player (“X”)). After the score for that move has been evaluated, the “O” is removed from the board. If a new “best_score” has been achieved, the “best_score” is updated to that value. “alpha” is updated to the best score achievable by the maximizing player. If “beta” is less than or equal to “alpha”, the loop will break as this is the beta cut-off point. This means that the function does not need to calculate scores for any more moves in this branch as they are “pruned”.

•	If the player is the minimizing player (the human player), the function will place an “X” in each cell that it iterates through. Next, it recursively calls the “minimax()” function with an increased depth and it switches to the maximizing player (the AI player (“O”)). After the score for that move has been evaluated, the “X” is removed from the board. If a new “best_score” has been achieved, the “best_score” is updated to that value. “beta” is updated to the best score achievable by the minimizing player. If “beta” is less than or equal to “alpha”, the loop will break as this is the beta cut-off point. This means that the function does not need to calculate scores for any more moves in this branch as they are “pruned”.

•	Finally, the function returns the value of the “best_score”.
### The main game loop
•	The main game loop runs as long as the game is active. Inside this loop, it constantly listens for events, such as mouse clicks (“pygame.MOUSEBUTTONDOWN”) or the game window closing (“pygame.QUIT”). 

•	The human player's moves are handled in response to mouse clicks. After the human player has made their move, the function checks if the game is over. If not, the AI will calculate its own next move and then make it by calling the “ai_turn()” function.

•	After each move, the board is updated with the new values.
### Displaying the result
•	The game state is checked after each move is made. If a win or tie condition is met, the game will end.

•	Once the game ends, it waits 1 second for the final moves to be displayed. The winner can either be the AI or the human player. If there is no winner, the game ends in a tie. After displaying the result, the game quits. The result is displayed on the screen for 3 seconds. The waiting times are managed by the “time.sleep()” function.

## 4	Training/Testing Strategy
### Initial Testing
We started by developing a Tic-Tac-Toe game where two humans can play against each other. The core functions of the game such as the game loop, event handling and the visual representation of the board were completed. Once the game was playable, we manually tested it with human players in order to ensure that it worked as expected. 
### AI Implementation and Testing
Once the game mechanics were in place, we implemented the AI player using the Minimax algorithm. As mentioned before, this algorithm was chosen because it is well-suited for games such as Tic-Tac-Toe. This is because it can exhaustively explore all possible game states. The Minimax algorithm was coded and incorporated into the existing (non-AI) Tic-Tac-Toe game. The AI was tested by different testers playing several rounds against it and observing its behaviour. All necessary modification and improvements were made.
### Algorithm Validation and Optimisation
We validated the effectiveness of the Minimax algorithm by playing a large number of games against the AI. The AI performed well, but it took some time to determine its first move. This is when we decided to incorporate Alpha-Beta pruning. Alpha-Beta pruning is an optimization technique for the Minimax search algorithm. It reduces the number of nodes that are evaluated. Using this technique can significantly improve the speed at which the game tree is searched. This will in turn, improve the user experience. Once the Alpha-Beta pruning was incorporated into our existing Minimax search algorithm, the AI player was able to make its moves in much shorter time, especially the first move. 
### Performance Testing
Response time was used to gauge the Minimax algorithm's effectiveness. Despite the short game tree of Tic-Tac-Toe, we made sure that the AI's moves were computed quickly enough to provide a good user experience. The performance of the AI was improved by incorporating Alpha-Beta Pruning. This is an important step as the nature of the problem we are trying to solve is educational. Knowing how Alpha-Beta Pruning works is an important step in understanding search techniques and therefore, AI. Even though including search optimisation techniques is not essential in a small search space such as is the case with tic-Tac-Toe, we decided to incorporate it as it is yet another additional AI technique that can be demonstrated in an easy-to-understand fashion.




