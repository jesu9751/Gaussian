# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm

1.Import the numpy module to use the built-in functions for calculation

2.Prepare the lists from each linear equations and assign in np.array()

3.Using the np.zeros() and seprate them and use it in the for loops so we can find the solutions

4.End the program 

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Jesu Joyal J
RegisterNumber: 212225040154
*/
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
n=int(input())
a = []
for i in range (n):
    row = []
    for j in range(n+1):
        row.append(float(input()))
    a.append(row)
for i in range(n):
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k] = a[j][k]-ratio*a[i][k]
x = [0]*n 
for i in range(n-1, -1, -1):
    x[i] = a[i][n]
    for j in range(i+1,n):
        x[i] -= a[i][j]*x[j]
    x[i] /= a[i][i]
for i in range(n):
    print("X{} = {:.2f}".format(i,x[i]),end=" ")
```

## Output:

<img width="1163" height="886" alt="image" src="https://github.com/user-attachments/assets/5ac7c89c-f47c-4445-9774-b10f22621afa" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

