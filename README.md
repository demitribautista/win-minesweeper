# Minesweeper for Windows

Using Visual Studio 2019 as the IDE and C# Programming Language


Minesweeper is a single-player puzzle video game. The objective of the game is to clear a
rectangular board containing hidden \mines" or bombs without detonating any of them, with
help from clues about the number of neighboring mines in each eld. The game originates
from the 1960s.
Minesweeper has a very basic gameplay style. In its original form, mines are scattered
throughout a board. This board is divided into cells, which have three states: uncovered,
covered and 
agged. A covered cell is blank and clickable, while an uncovered cell is exposed,
either containing a number (the mines adjacent to it), or a mine. When a cell is uncovered
by a player click, and if it bears a mine, the game ends. A 
agged cell is similar to a covered
one, in the way that mines are not triggered when a cell is 
agged, and it is impossible to
lose through the action of 
agging a cell. However, 
agging a cell implies that a player thinks
there is a mine underneath, which causes the game to deduct an available mine from the
display.

In order to win the game, players must logically deduce where mines exist through the
use of the numbers given by uncovered cells. To win, all non-mine cells must be uncovered.
At this stage, the timer is stopped. Commonly all mine cells are also agged, but this is not required.

The main form of the application includes the following control objects:
One System.Windows.Forms.TextBox object for displaying the number of currently
open games.
One System.Windows.Forms.TextBox object for receiving the player name from the
user.
Four radio buttons for labels Easy, Medium, Expert, and Custom (by default, Medium
is checked).
One System.Windows.Forms.Button object to start a new game.
One System.Windows.Forms.Button object to end all currently open games.
One System.Windows.Forms.MenuStrip object with items \Play a new game", \Close
all games", "Exit". The first item has a sub-menu containing "Easy", "Medium", and
"Expert".

A click on the "Play a new game"  results in one of these possibilities:
If any radio button except \Custom" is checked, a new form containing an empty board
is shown, but a new game has not started yet.

If "Custom" radio button is checked, a dialog must appear on screen and asks user to
input three parameters: int row (# of rows of the game board), int col (# of columns
of the game board), and int mines (# of mines in the game board). If any negative
number is entered, row*col < 18, or mines > row*col/2, then the user should be asked

The \Easy" game parameters are row = col = 9, and mines = 10. The \Medium" game
parameters are row = col = 16, and mines = 40. The \Expert" game parameters are row =
30, col = 16, and mines = 99.

# The Game: From the Beginning to End

The game board is made of row*col buttons, a display showing the clock and another display
showing the number of mines minus the number of flags. The game (and clock) starts when
the player makes the first left-click" on one of the buttons on the board. At this moment,
the mines get uniformly, but randomly distributed over the board in a way that no mines
are placed on the first-click square and its surrounding squares (see the code for details).

A right-click on a covered cell will place a flag on that cell. You can run the incomplete
implementation and try the middle-click on a cell to see what happens.

When a game is lost or won, the game form will be closed with a \You lost!" or \You won in XY seconds!". If the user wants to close a game that has been started, the program asks user if he/she is sure before closing it.
