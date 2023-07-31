# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Read the matrix input from the user or define it as a list of lists.
2. Perform forward elimination to convert the matrix to upper triangular form.
   - Iterate over every row in the matrix, starting from the first row.
   - If the element in the first column of the current row is zero, swap it with a non-zero element from a lower row.
   - Iterate over every row below the current row and subtract a multiple of the current row from each row, such that the first element becomes zero.
3. Perform back substitution to find the solution.
   - Start from the last row and substitute the values of the variables one by one.
   - Substitute the known values of the variables in the current row equation and solve for the current variable.
   - Substitute the found value of the current variable in previous row equations and solve for other variables.
4. Print the solution or use it for further calculations.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Karthick Raja K
RegisterNumber: 23006120
import numpy as np
import sys

n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)

for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
        
for i in range(n):
    if a[i][i]==0.0:
        sys.exit("divide ny zero detected")
        
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]

for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
        
    x[i]=x[i]/a[i][i]
    
for i in range(n):
    print("X%d = %0.2f"%(i,x[i]),end=' ')

*/
```

## Output:
![gaussian elimination](/Screenshot%202023-07-31%20184116.png)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

