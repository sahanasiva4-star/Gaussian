# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
~~~
1. Import the necessary libraries(numpy,scipy.linalg) to use the built-in functions for calculation
2. Prepare the lists from each linear equations and assign in np.array()
3. Using the lu(), lu_solve(), lu_factor(), we can find the solutions.
4. End the program
~~~

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: SAHANA S
RegisterNumber: 212225230236
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
n=int(input())
matrix=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        matrix[i][j]=int(input())
for i in range(n):
    for j in range(i+1,n):
        ratio=matrix[j][i]/matrix[i][i]
        for k in range(n+1):
            matrix[j][k]=matrix[j][k]-ratio*matrix[i][k]
#Back Substitution
x[n-1]=matrix[n-1][n]/matrix[n-1][n-1]
for i in range (n-2,-1,-1):
    x[i]=matrix[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-matrix[i][j]*x[j]
    x[i]=x[i]/matrix[i][i]
for i in range(n):
    print("X%d = %0.2f"%(i,x[i]),end=" ")
```

## Output:
<img width="1023" height="436" alt="image" src="https://github.com/user-attachments/assets/2968a36b-1ddc-4fcd-a16e-9a290ec095a7" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

