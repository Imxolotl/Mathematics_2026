# Problem 2: Gaussian Elimination — One Solution

## Question

Solve using Gaussian elimination:

$$
\begin{cases}
x+y+z=6, \\
2x-y+z=3, \\
x+2y-z=2.
\end{cases}
$$

After solving, substitute the result into all equations and check consistency.

---

## Solution

### 1. Set Up the Augmented Matrix

We write the linear system as an augmented matrix $[A \mid b]$:

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 6 \\
2 & -1 & 1 & \mid & 3 \\
1 & 2 & -1 & \mid & 2
\end{pmatrix}
$$

---

### 2. Forward Elimination to Row Echelon Form

#### Step 1: Create zeros under the first pivot ($a_{11} = 1$)

We eliminate the $x$-coefficients from rows 2 and 3 using the elementary row operations:

- $R_2 \leftarrow R_2 - 2R_1$:

$$
(2 - 2(1), \; -1 - 2(1), \; 1 - 2(1) \mid 3 - 2(6)) = (0, -3, -1 \mid -9)
$$

- $R_3 \leftarrow R_3 - R_1$:

$$
(1 - 1(1), \; 2 - 1(1), \; -1 - 1(1) \mid 2 - 1(6)) = (0, 1, -2 \mid -4)
$$

The augmented matrix becomes:

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 6 \\
0 & -3 & -1 & \mid & -9 \\
0 & 1 & -2 & \mid & -4
\end{pmatrix}
$$

#### Step 2: Swap rows for a simpler pivot

Swap row 2 and row 3 ($R_2 \leftrightarrow R_3$) to bring the leading coefficient $1$ into the second row:

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 6 \\
0 & 1 & -2 & \mid & -4 \\
0 & -3 & -1 & \mid & -9
\end{pmatrix}
$$

#### Step 3: Eliminate the entry below the second pivot

Eliminate the entry in row 3, column 2 using $R_3 \leftarrow R_3 + 3R_2$:

$$
(0 + 3(0), \; -3 + 3(1), \; -1 + 3(-2) \mid -9 + 3(-4)) = (0, 0, -7 \mid -21)
$$

The augmented matrix is now in upper triangular (row echelon) form:

$$
\begin{pmatrix}
1 & 1 & 1 & \mid & 6 \\
0 & 1 & -2 & \mid & -4 \\
0 & 0 & -7 & \mid & -21
\end{pmatrix}
$$

---

### 3. Back-Substitution

We convert the row echelon matrix back into equations and solve from the bottom up.

#### Solve for $z$:

From row 3:

$$
-7z = -21 \implies z = \frac{-21}{-7} = 3
$$

#### Solve for $y$:

From row 2:

$$
y - 2z = -4
$$

Substitute $z = 3$:

$$
y - 2(3) = -4 \implies y - 6 = -4 \implies y = 2
$$

#### Solve for $x$:

From row 1:

$$
x + y + z = 6
$$

Substitute $y = 2$ and $z = 3$:

$$
x + 2 + 3 = 6 \implies x + 5 = 6 \implies x = 1
$$

---

### 4. Final Solution

The system has exactly one unique solution:

$$
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix}
= \begin{pmatrix}
1 \\
2 \\
3
\end{pmatrix}
$$

or simply $(x, y, z) = (1, 2, 3)$.

---

## Verification and Consistency Checks

We substitute $(x, y, z) = (1, 2, 3)$ into each of the original three equations.

### Equation 1: $x + y + z = 6$

$$
1 + 2 + 3 = 6
$$

Both sides equal $6$. The equation is satisfied.

### Equation 2: $2x - y + z = 3$

$$
2(1) - 2 + 3 = 2 - 2 + 3 = 3
$$

Both sides equal $3$. The equation is satisfied.

### Equation 3: $x + 2y - z = 2$

$$
1 + 2(2) - 3 = 1 + 4 - 3 = 2
$$

Both sides equal $2$. The equation is satisfied.

All three equations are satisfied simultaneously, confirming that $(1, 2, 3)$ is the correct and unique solution.

---

## Why This Exercise Matters

1. **Systematic Procedure:** Gaussian elimination transforms any linear system into an upper triangular system where the solution can be found directly through backward substitution without trial and error.
2. **Pivoting Strategy:** Swapping rows to obtain a pivot of $1$ simplifies manual arithmetic and reduces fraction operations.
3. **Verification Habit:** Substituting the obtained values back into all original equations serves as an independent check that guarantees arithmetic accuracy.
