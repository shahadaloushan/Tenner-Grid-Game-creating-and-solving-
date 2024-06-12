# Tenner Grid Game creating and solving
This Python project provides a solver for the Tenner Grid puzzle using various search algorithms, including Simple Backtracking, Forward Checking, and Forward Checking with Minimum Remaining Values (MRV). The Tenner Grid puzzle involves filling in a grid of cells with numbers from 0 to 9, subject to certain constraints, such as row uniqueness and column sums



## Usage
To use the solver, run the main() function in the tenner_solver.py file. This will generate a random Tenner Grid puzzle, solve it using each of the implemented algorithms, and print the solved grid along with statistics such as assignment counts, consistency checks, and elapsed time.

# Project Explenation 
## 1. Backtracking:
a) Initialization: Begin with an empty grid and start filling cells one by one.


 b) Value Selection:For each cell, choose a value from its domain. Since the initial grid is
empty, the domain for each cell initially contains all possible values (0 to 9).


 c) Constraint Checking: Once a value is selected for a cell, check if it satisfies the following
constraints:


d) Column Sum Constraints: Ensure that adding the selected value to the current row and
column does not exceed the predefined sums.


e) Adjacent Cell Constraint: Verify that the selected value does not conflict with the values
in adjacent cells (cells sharing a side or a corner).


f) Recursion: If the selected value satisfies all constraints, recursively move on to the next
cell and repeat the process until all cells are filled.


g) Backtracking: If a selected value violates any constraint, backtrack to the previous cell
and try a different value from its domain. Repeat this process until a valid solution is
found or all possibilities are exhausted.


h) Conclusion: Simple backtracking systematically explores the solution space by trying out
different combinations of values for each cell while ensuring that all constraints are met.

It efficiently searches for a valid solution but may take longer for complex problems or instances with a large search space.

## 2. Forward Checking:
a) Initialization: Begin with an empty grid and start filling cells one by one.


b) Value Selection: For each cell, choose a value from its domain. Initially, the domain for
each cell contains all possible values (0 to 9).


c) Constraint Checking: Once a value is selected for a cell, check if it satisfies the
constraints as in the backtracking algorithm.


d) Domain Update: After assigning a value to a cell, update the domains of other unassigned
cells in the same row and column. Remove values from their domains that conflict with
the current assignment.


e) Recursion: If the selected value satisfies all constraints, recursively move on to the next
cell and repeat the process.


f) Backtracking: If a selected value violates any constraint, backtrack to the previous cell
and try a different value from its domain. Repeat this process until a valid solution is
found or all possibilities are exhausted.


g) Conclusion: Forward Checking enhances the efficiency of the backtracking algorithm by
dynamically reducing the search space through constraint propagation. 

It effectively prunes the search tree by eliminating values from the domains of unassigned variables that are inconsistent with the current assignments, leading to faster convergence towards a valid solution.
## 3. Forward Checking with MRV:
a) Initialization: Begin with an empty grid and start filling cells one by one.


b) Variable Selection: Instead of choosing cells arbitrarily, select the most constrained
variable, i.e., the cell with the smallest domain size.


c) Value Selection: For the selected cell, choose a value from its domain.


d) Constraint Checking: Verify if the selected value satisfies all constraints.


e) Domain Update: Update the domains of other unassigned cells based on the current
assignment, ensuring consistency with the constraints.


f) Recursion: If the selected value satisfies all constraints, recursively move on to the next
cell and repeat the process.

g) Backtracking: If a selected value violates any constraint, backtrack to the previous cell and try a different value. Repeat this process until a valid solution is found or all possibilities are exhausted.


h) Conclusion:Forward Checking with MRV enhances the efficiency of the backtracking algorithm by prioritizing the selection of variables with the fewest remaining legal values. 


By minimizing the branching factor, it accelerates the search process and leads to faster convergence towards a valid solution. This approach is particularly effective for problems with a large search space and complex constraints.
