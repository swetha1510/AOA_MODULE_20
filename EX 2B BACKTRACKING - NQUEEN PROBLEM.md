# EX 2B BACKTRACKING - NQUEEN PROBLEM
## DATE:
## AIM:
To solve the N-Queen problem using backtracking, which places N queens on an N*N chessboard such that no two queens threaten each other.

## Algorithm
1.Start with an empty board — no queens placed yet.

2.Go column by column, from left to right.

3.In each column, try placing a queen in every row, one by one.

4.Before placing a queen, check:

5.If the position is safe, place the queen.

6.Then, move to the next column and repeat the same steps.

7.If you reach the last column and place a queen, you’ve found a solution!

8.If you can't place a queen in any row of a column, go back to the previous column and move the queen to the next possible row — this is called backtracking.

9.Keep trying until:You place queens in all columns successfully (solution found), (or) you try every possibility and find that no solution exists.

10.Print the board showing where the queens are placed (with 1s), or print "No solution" if it doesn't work.
## Program:
```
# Developed by: SWETHA P
# Register Number:  212222100053

global N
N = int(input())
 
def printSolution(board):
    for i in range(N):
        for j in range(N):
            print(board[i][j], end = " ")
        print()
 
def isSafe(board, row, col):
 
    # Check this row on left side
    for i in range(col):
        if board[row][i] == 1:
            return False
 
    # Check upper diagonal on left side
    for i, j in zip(range(row, -1, -1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    # Check lower diagonal on left side
    for i, j in zip(range(row, N, 1),
                    range(col, -1, -1)):
        if board[i][j] == 1:
            return False
 
    return True
 
def solveNQUtil(board, col):
    if col>=N:
        return True
    
    for row in range(N):
        if isSafe(board,row,col):
            board[row][col]=1
            if solveNQUtil(board, col+1):
                return True
            board[row][col]=0
    return False        

def solveNQ():
    board = [ [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0],
              [0, 0, 0, 0, 0, 0, 0, 0]]
 
    if solveNQUtil(board, 0) == False:
        print ("Solution does not exist")
        return False
 
    printSolution(board)
    return True
 
# Driver Code
solveNQ()
```

## Output:
![438782658-38382176-f742-4706-96a2-e72cf56cd1e8](https://github.com/user-attachments/assets/1a4e0599-fa5c-44f4-92a3-4151c4a62463)


## Result:
The N-Queens program executed successfully, and a valid board configuration was generated.
