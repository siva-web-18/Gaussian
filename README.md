# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
## Algorithm: Gaussian Elimination Method

### Step 1:

Start the program.

### Step 2:

Read the number of unknowns `n`.

### Step 3:

Input the augmented matrix `A[n][n+1]`.

### Step 4:

Apply forward elimination to convert the matrix into upper triangular form.

For `i = 0` to `n-1`:

* For `j = i+1` to `n-1`:

  * Find the factor:

  [
  factor = \frac{A[j][i]}{A[i][i]}
  ]

  * For `k = 0` to `n`:

  [
  A[j][k] = A[j][k] - factor \times A[i][k]
  ]

### Step 5:

Apply back substitution to find the unknown values.

* Set:

[
x[n-1] = \frac{A[n-1][n]}{A[n-1][n-1]}
]

* For `i = n-2` down to `0`:

[
x[i] = \frac{A[i][n] - \sum (A[i][j] \times x[j])}{A[i][i]}
]

### Step 6:

Display the values of all unknowns.

### Step 7:

Stop the program.


## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: siva 
RegisterNumber: 212225100050
*/
n = int(input())

# Read augmented matrix
a = []
for i in range(n):
    row = []
    for j in range(n + 1):
        row.append(float(input()))
    a.append(row)

# Gaussian Elimination
for i in range(n - 1):
    for j in range(i + 1, n):
        factor = a[j][i] / a[i][i]

        for k in range(n + 1):
            a[j][k] = a[j][k] - factor * a[i][k]

# Back Substitution
x = [0] * n

for i in range(n - 1, -1, -1):
    s = a[i][n]

    for j in range(i + 1, n):
        s = s - a[i][j] * x[j]

    x[i] = s / a[i][i]

# Output
for i in range(n):
    print(f"X{i} = {x[i]:.2f}", end=" ")
```

## Output:
![gaussian elimination]()

<img width="1190" height="843" alt="Screenshot 2026-05-19 200206" src="https://github.com/user-attachments/assets/9d352b24-82ac-4947-a707-8cca7546b4be" />
<img width="819" height="570" alt="Screenshot 2026-05-19 200212" src="https://github.com/user-attachments/assets/5fa23b62-36d2-4612-b08f-72f2927ccb19" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

