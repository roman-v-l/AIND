# Artificial Intelligence Nanodegree
## Introductory Project: Diagonal Sudoku Solver

# Question 1 (Naked Twins)
Q: How do we use constraint propagation to solve the naked twins problem?  
A: Naked Twins is one of Sudoku solving techniques that, when applied repeatedly along with other techniques to every
square, significantly reduce the search space. Every square in a Sudoku board has constraints enforced by the
rules of the game. One of the constraints is when two squares of a unit (i.e. a column, row or 3x3 block) has exactly two
possible values that can be assigned to the squares, those values may not be assigned to the rest of the squares in the
unit. We call such pairs of squares Naked Twins. So the Naked Twins elimination technique works as follows:

  1. We pick a unit and look for naked twins in the unit. Please note, there can be more than one pair of naked twins
     in the unit.
  2. If we find one of more pairs of naked twins, we loop over the rest of the non-filled squares in the unit and
     remove the naked twins values from the list of possible values of the squares.

Reducing the number of options results in assigning values to some of the unit's squares (the ones that had exactly 3
possible values before) or it could open up possibilities for further reducing when we enforce the constraints
repeatedly to this and other board's units. For instance, if a square had 4 possible values before enforcing
Naked Twins and 2 after that, it could in turn become one of naked twins in other units of the board.
Constraint propagation is about applying this and other techniques to the board squares repeatedly until we get a
solution or none of the techniques changes anything on the board. In the end, we still may need to use the recursive
search but with a potentially much smaller search tree.

# Question 2 (Diagonal Sudoku)
Q: How do we use constraint propagation to solve the diagonal sudoku problem?  
A: A diagonal sudoku can be resolved using the same constraint propagation techniques as a regular sudoku: we apply
repeatedly the available options elimination techniques ("one-digit elimination", "only choice", "naked twins")
to every square of the board. The only difference is that we have two additional board units to analyze.
So 17 squares on two main diagonals will have additional constraints to enforce. A diagonal sudoku may have smaller
number of possible solutions than the corresponding regular sudoku due to additional constraints and, technically,
it should be resolved faster than the regular one using constraint propagation.

### Install

This project requires **Python 3**.

We recommend students install [Anaconda](https://www.continuum.io/downloads), a pre-packaged Python distribution that contains all of the necessary libraries and software for this project. 
Please try using the environment we provided in the Anaconda lesson of the Nanodegree.

##### Optional: Pygame

Optionally, you can also install pygame if you want to see your visualization. If you've followed our instructions for setting up our conda environment, you should be all set.

If not, please see how to download pygame [here](http://www.pygame.org/download.shtml).

### Code

* `solutions.py` - You'll fill this in as part of your solution.
* `solution_test.py` - Do not modify this. You can test your solution by running `python solution_test.py`.
* `PySudoku.py` - Do not modify this. This is code for visualizing your solution.
* `visualize.py` - Do not modify this. This is code for visualizing your solution.

### Visualizing

To visualize your solution, please only assign values to the values_dict using the ```assign_values``` function provided in solution.py

### Data

The data consists of a text file of diagonal sudokus for you to solve.