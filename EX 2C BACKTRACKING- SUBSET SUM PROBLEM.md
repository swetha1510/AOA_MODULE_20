# EX 2C BACKTRACKING- SUBSET SUM PROBLEM
## DATE:
## AIM:
To demonstrate that the sum of the subset of a given set is equal to the given sum.


## Algorithm
1.Start with the first number in the list and a running total of 0.

2.At each number, you have two choices:

3.Include the number in the sum.

4.Move to the next number and repeat the process for both choices.

5.Keep doing this until,You reach the end of the list.

6.At that point, check if the current sum equals the target.

7.If you ever reach the target sum, return True (meaning a valid subset was found).

8.If all possibilities are tried and none of them match the target, return False.

9.At the end, print the original list and show whether a valid subset exists.

## Program:
```
# Developed by: SWETHA P 
# Register Number:  212222100053

def SubsetSum(a,i,sum,target,n):
    if i == n:
        return sum == target
    
    if SubsetSum(a,i+1,sum+a[i],target,n):   
        return True
        
    if SubsetSum(a,i+1,sum,target,n):   
        return True 
        
    return False    
    
a=[]
size=int(input())
for i in range(size):
    x=int(input())
    a.append(x)

target=int(input())
n=len(a)

if(SubsetSum(a,0,0,target,n)==True):
    for i in range(size):
        print(a[i])
    print("True,subset found")
else:
    for i in range(size):
        print(a[i])
    print("False,subset not found")

```
## Output:

![438785010-41e1249b-cdae-4069-b882-b23602345d76](https://github.com/user-attachments/assets/b78047f2-3979-40a7-833a-2e077214871e)

## Result:
The Subset Sum program executed successfully, and the result was determined based on whether a subset matching the target sum was found or not.
