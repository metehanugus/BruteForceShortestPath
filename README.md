# BruteForceShortestPath
A C++ program that will find a path for a scenario described in readme. It uses Brute Force.

"A hero is surrounded by monsters in a forest. He doesn't have too much energy left to fight.
 He wants to profit as much as possible. He is a prodigy so, he will find the most efficient way to do that
 by calculating every possible outcome"


/*
 * Mandatory variables
 * emptySymbol = ' '
 * heroSymbol = 'H'
 * monsterSymbol = 'M'
 * STAMINA = 10
 * MONSTER_REWARD = 5
*/

/* Restrictions
 * Hero has a {STAMINA} amount of stamina.
 * Hero can spawn near a monster.
 * Moving each square decreases one stamina.
 * Moving on monster symbol grants the hero a {MONSTER_REWARD} amount of gold.
 * Hero can move in left, right, up, and down directions.
 * Hero cannot slay the same monster more than once.
 * When the hero's stamina reaches 0, he can not move further; however, he can slay the monster in the square and earn money.
 * Write a brute-force algorithm to calculate the most profiting path from the hero's starting position, and print it with the money earned.
 * Check example_output.txt for further details.
*/

/* Fill game area with emptySymbol
 * game area is {FIRST_DIMENSION} x {SECOND_DIMENSION} grid (or in programming terms 2 dimensional array)
 *  where the FIRST_DIMENSION and SECOND_DIMENSION parameters are constant variables with the initial value
 *  of 8 and 8. You have to use global constants so that If I want to test something, I can easily change the
 * dimensional values.
*/
void fillGameArea();

// Prints the game area
void printGameArea();

// Checks that if the given coordinate (row,column) in the bound of game area.
bool isValidCoordinate(int row, int column);

// Checks that if the given position is suitable to place a monster
// The position must be valid and empty
bool validMonsterPosition(int row, int column);


/* There must be 5 monsters, and each of them should be at least 2 square apart (diagonals included, the second square is not allowed)
 * to each other in every direction.
 * Monster positions will be assigned randomly to suitable squares
 * You can use import random in the desired language.
*/
void assignMonsters();

// Assigns hero to a random suitable position and returns the coordinate.
// I advise you to create a simple Coordinate structure to store the position but, it is not mandatory to do that.
Coordinate *assignHero();


Example Output:

   0  1  2  3  4  5  6  7
0 [ ][ ][ ][ ][ ][ ][ ][ ]

1 [M][ ][ ][ ][ ][ ][ ][M]

2 [ ][H][ ][ ][ ][ ][ ][ ]

3 [ ][ ][ ][ ][ ][ ][ ][ ]

4 [ ][ ][M][ ][ ][ ][ ][M]

5 [ ][ ][ ][ ][ ][ ][ ][ ]

6 [ ][ ][ ][ ][ ][ ][ ][ ]

7 [ ][ ][M][ ][ ][ ][ ][ ]

Maximum possible gold  : 15
Best path : -L-U-D-D-D-R-R-D-D-D
