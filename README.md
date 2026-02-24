# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Read matrix 𝐴 and vector B. Form the augmented matrix [A∣B].
2. Forward Elimination:
For k = 0 to n-2
For i = k+1 to n-1
Compute factor
factor = A[i][k] / A[k][k]
For j = k to n A[i][j] = A[i][j] - factor * A[k][j]

3. Back Substitution:
x[n-1] = A[n-1][n] / A[n-1][n-1]
For i = n-2 to 0
sum = 0
For j = i+1 to n-1
sum = sum + A[i][j] * x[j]
x[i] = (A[i][n] - sum) / A[i][i]

4. Print the solution vector X

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Akshaya Sree G
RegisterNumber:212225230011 
*/
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
        sys.exit('Divide by zero detected')
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range (i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f'%(i,x[i]),end=' ')
```

## Output:
![gaussian elimination]()
<img width="940" height="548" alt="image" src="https://github.com/user-attachments/assets/ea1e5fd7-f5d4-4f94-9f81-d1adc095398c" />


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

