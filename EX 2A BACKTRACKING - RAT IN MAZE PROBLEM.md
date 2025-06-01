# EX 2A BACKTRACKING - RAT IN MAZE PROBLEM
## DATE:
## AIM:
To implement the Rat in a Maze problem using backtracking and find all possible paths from the start to the destination in a given maze.


## Algorithm
1.Initialize a solution matrix sol[N][N] with all zeros.

2.Start from cell (0, 0) — check if it is safe to enter:

3.Use isSafe(maze, x, y) to check if the cell is inside the grid and its value is 1.

4.Define recursive function solveMazeUtil(x, y, sol):

5.If x == N-1 and y == N-1, i.e., destination is reached:

6.Mark sol[x][y] = 1 and return True.

7.Mark current cell in solution path: sol[x][y] = 1.

8.Try moving in two directions:

9.First, try moving down (x+1, y). If this leads to a solution, return True.

10.If not, try moving right (x, y+1). If this leads to a solution, return True.

11.Backtrack: Unmark this cell in the solution (sol[x][y] = 0) and return False.

12.If no path is found starting from (0, 0), print "Solution doesn't exist".

13.If a path is found, print the solution matrix, where 1 marks the path from start to goal. 

## Program:
```
 Developed by: SWETHA P 
 Register Number:  212222100053
```
```
N = 4
def printSolution( sol ):
    for i in sol:
        for j in i:
            print(str(j) + " ", end ="")
        print("")
        
def isSafe( maze, x, y ):
     
    if x >= 0 and x < N and y >= 0 and y < N and maze[x][y] == 1:
        return True
     
    return False
    
def solveMaze( maze ):
    sol = [ [ 0 for j in range(4) ] for i in range(4) ]
     
    if solveMazeUtil(maze, 0, 0, sol) == False:
        print("Solution doesn't exist");
        return False
     
    printSolution(sol)
    return True
     
# A recursive utility function to solve Maze problem
def solveMazeUtil(maze, x, y, sol):
    if not isSafe(maze,x,y):
        return False
        
    # if (x, y is goal) return True
    if x == N - 1 and y == N - 1:
        sol[x][y] = 1
        return True
    sol[x][y]=1    
     
    if solveMazeUtil(maze, x+1, y, sol):
        return True
    
    if solveMazeUtil(maze, x, y+1, sol):
        return True
    
    sol[x][y]=0
    return False

if __name__ == "__main__":
    maze = [ [1, 0, 0, 0],
             [1, 1, 0, 1],
             [0, 1, 0, 0],
             [1, 1, 1, 1] ]
              
    solveMaze(maze)
```
## Output:
![438777388-ec71b7fe-ca2c-42b9-8aa5-8efcd9705ba0](https://github.com/user-attachments/assets/a4db67c7-668b-48e3-b547-93c947b56ae7)

## Result:
The Rat in a Maze program executed successfully, and a valid path from the start to the destination was found and display.
