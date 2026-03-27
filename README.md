# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
```
Step 1: Start the program.
Step 2: Read the number of unknowns n
Step 3: Input the augmented matrix (coefficients and constants).
Step 4: Perform forward elimination:
For each row, make the elements below the main diagonal equal to zero
Do this by performing row operations (interchanging, multiplying, subtracting rows if needed)
Step 5: After elimination, the matrix will be in upper triangular form.
Step 6: Perform back substitution:
Start from the last equation
Find the value of each variable one by one
Substitute the known values into the above equations
Step 7: Obtain all the unknown values.
Step 8: Display the solution.
Step 9: Stop the program.
```

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

