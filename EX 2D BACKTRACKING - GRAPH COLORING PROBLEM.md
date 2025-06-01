# EX 2D BACKTRACKING - GRAPH COLORING PROBLEM
## DATE:
## AIM:
To solve the Graph Coloring Problem using backtracking, assigning colors to the vertices of a graph such that no two adjacent vertices share the same color while minimizing the number of colors used.



## Algorithm
1.Create a graph with V vertices and an adjacency matrix showing which vertices are connected.

2.Prepare a list of colors, initially set to 0 (uncolored) for each vertex.

3.Start from the first vertex (v = 0) and try all colors from 1 to m.

4.For each color,Check if it is safe to use on the current vertex by checking all previously colored (connected) vertices.

5.If no connected vertex has the same color, assign this color.

6.Then, move to the next vertex and repeat the coloring process.

7.If all vertices are successfully colored following the rules, print the assigned colors — solution exists.

8.If you reach a point where no color can be safely assigned, go back to the previous vertex and try a different color — this is backtracking.

9.If no valid coloring is found, print “No solution exists.”

## Program:
```
# Developed by: SWETHA P
# Register Number:  212222100053

class Graph:
    def __init__(self,vertices):
        self.V=vertices
        self.graph=[[0 for row in range(vertices)] for column in range(vertices)]
        
    def isSafe(self,v,colour,c):
        for i in range(v):
            if self.graph[v][i]==1 and colour[i]==c:
                return False
        return True
        
    def graphColourUtil(self,m,colour,v):
        if v==self.V:
            return True 
        for i in range(1,m+1):
            if self.isSafe(v,colour,i):
                colour[v]=i
                if self.graphColourUtil(m,colour,v+1):
                    return True
        return False
        
    def graphColouring(self,m):
        colour=[0]*self.V
        if not self.graphColourUtil(m,colour,0):
            print("No solution Exist")
            return False
        print("Solution exist and Following are the assigned colours:")
        
        for c in colour:
            print(c,end=' ')
        print()
        return True
    

```

## Output:
![438786406-a31a11e8-10fe-4558-922f-cc1c70093d25](https://github.com/user-attachments/assets/01faf22b-7448-4efe-a778-e9bb145f4f43)


## Result:
The Graph Coloring program executed successfully, and the colors were assigned to the vertices such that no two adjacent vertices share the same color.
