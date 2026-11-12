# Problem 8: Two Systems with the Same Coefficient Matrix

## Question

Solve by elimination the two systems

$$
\begin{cases}
2x+y=5, \\
x-y=1,
\end{cases}
$$

$$
\begin{cases}
2x+y=1, \\
x-y=4.
\end{cases}
$$

Compare the successive elimination steps. Which part of the calculation is the same in both cases, and why?

---

## Solution

### 1. Structure of the Systems

Both systems share the identical $2 \times 2$ coefficient matrix:

$$
A =
\begin{pmatrix}
2 & 1 \\
1 & -1 \\
\end{pmatrix}
$$

They differ only in their right-hand side constant vectors:

$$
b_1 =
\begin{pmatrix}
5 \\
1 \\
\end{pmatrix},
\qquad
b_2 =
\begin{pmatrix}
1 \\
4 \\
\end{pmatrix}
$$

---

### 2. Solving System 1

The augmented matrix for the first system is:

$$
\begin{pmatrix}
2 & 1 & \mid & 5 \\
1 & -1 & \mid & 1 \\
\end{pmatrix}
$$

#### Step 1: Swap rows to obtain pivot $1$ ($R_1 \leftrightarrow R_2$)

$$
\begin{pmatrix}
1 & -1 & \mid & 1 \\
2 & 1 & \mid & 5 \\
\end{pmatrix}
$$

#### Step 2: Eliminate $x$ from row 2 ($R_2 \leftarrow R_2 - 2R_1$)

$$
R_2 - 2R_1 = (2 - 2(1), \; 1 - 2(-1) \mid 5 - 2(1)) = (0, \; 3 \mid 3)
$$

The echelon form is:

$$
\begin{pmatrix}
1 & -1 & \mid & 1 \\
0 & 3 & \mid & 3 \\
\end{pmatrix}
$$

#### Step 3: Back-substitution

- From row 2:

$$
3y = 3 \implies y = 1
$$

- From row 1:

$$
x - y = 1 \implies x - 1 = 1 \implies x = 2
$$

The solution to System 1 is:

$$
\begin{pmatrix}
x \\
y \\
\end{pmatrix}
= \begin{pmatrix}
2 \\
1 \\
\end{pmatrix}
$$

---

### 3. Solving System 2

The augmented matrix for the second system is:

$$
\begin{pmatrix}
2 & 1 & \mid & 1 \\
1 & -1 & \mid & 4 \\
\end{pmatrix}
$$

#### Step 1: Swap rows to obtain pivot $1$ ($R_1 \leftrightarrow R_2$)

$$
\begin{pmatrix}
1 & -1 & \mid & 4 \\
2 & 1 & \mid & 1 \\
\end{pmatrix}
$$

#### Step 2: Eliminate $x$ from row 2 ($R_2 \leftarrow R_2 - 2R_1$)

$$
R_2 - 2R_1 = (2 - 2(1), \; 1 - 2(-1) \mid 1 - 2(4)) = (0, \; 3 \mid -7)
$$

The echelon form is:

$$
\begin{pmatrix}
1 & -1 & \mid & 4 \\
0 & 3 & \mid & -7 \\
\end{pmatrix}
$$

#### Step 3: Back-substitution

- From row 2:

$$
3y = -7 \implies y = -\frac{7}{3}
$$

- From row 1:

$$
x - y = 4 \implies x = 4 + y = 4 - \frac{7}{3} = \frac{5}{3}
$$

The solution to System 2 is:

$$
\begin{pmatrix}
x \\
y \\
\end{pmatrix}
= \begin{pmatrix}
\frac{5}{3} \\
-\frac{7}{3} \\
\end{pmatrix}
$$

---

### 4. Solving Both Systems Simultaneously (Dual Augmented Matrix)

Because the elimination steps depend only on $A$, we can solve both systems at the same time using a single dual augmented matrix $[A \mid b_1 \mid b_2]$:

$$
\begin{pmatrix}
2 & 1 & \mid & 5 & 1 \\
1 & -1 & \mid & 1 & 4 \\
\end{pmatrix}
$$

Applying $R_1 \leftrightarrow R_2$:

$$
\begin{pmatrix}
1 & -1 & \mid & 1 & 4 \\
2 & 1 & \mid & 5 & 1 \\
\end{pmatrix}
$$

Applying $R_2 \leftarrow R_2 - 2R_1$:

$$
\begin{pmatrix}
1 & -1 & \mid & 1 & 4 \\
0 & 3 & \mid & 3 & -7 \\
\end{pmatrix}
$$

Dividing row 2 by $3$ ($R_2 \leftarrow \frac{1}{3}R_2$):

$$
\begin{pmatrix}
1 & -1 & \mid & 1 & 4 \\
0 & 1 & \mid & 1 & -\frac{7}{3} \\
\end{pmatrix}
$$

Adding row 2 to row 1 ($R_1 \leftarrow R_1 + R_2$):

$$
\begin{pmatrix}
1 & 0 & \mid & 2 & \frac{5}{3} \\
0 & 1 & \mid & 1 & -\frac{7}{3} \\
\end{pmatrix}
$$

The two solution vectors appear immediately as the two columns on the right: $(2, 1)^T$ and $(\frac{5}{3}, -\frac{7}{3})^T$.

---

## Comparison and Analysis

### Which part of the calculation is identical?
- The row operations performed on the coefficient part of the matrix:
  1. The row swap $R_1 \leftrightarrow R_2$.
  2. The elimination multiplier $m_{21} = 2$ and the operation $R_2 \leftarrow R_2 - 2R_1$.
  3. The resulting coefficient echelon matrix:

$$
\begin{pmatrix}
1 & -1 \\
0 & 3 \\
\end{pmatrix}
$$

### Why is this part identical?
The sequence of elementary row operations in Gaussian elimination is determined solely by the positions and values of the entries in the coefficient matrix $A$. The goal of elimination is to produce zeros below the main diagonal in $A$.

The right-hand side vectors ($b_1$ and $b_2$) are transformed passively by these operations; they receive the operations but do not determine which operations are performed.

---

## Verification and Consistency Checks

### Check System 1 with $(x, y) = (2, 1)$:
- $2x + y = 2(2) + 1 = 5 \quad \checkmark$
- $x - y = 2 - 1 = 1 \quad \checkmark$

### Check System 2 with $(x, y) = (\frac{5}{3}, -\frac{7}{3})$:
- $2x + y = 2\left(\frac{5}{3}\right) + \left(-\frac{7}{3}\right) = \frac{10 - 7}{3} = \frac{3}{3} = 1 \quad \checkmark$
- $x - y = \frac{5}{3} - \left(-\frac{7}{3}\right) = \frac{5 + 7}{3} = \frac{12}{3} = 4 \quad \checkmark$

Both solution vectors satisfy their respective systems perfectly.

---

## Why This Exercise Matters

1. **Independence of Matrix Operations:** The mechanical work of transforming $A$ to echelon form depends only on the system's coefficients, not on the constants.
2. **Foundation for Multiple Right-Hand Sides:** This principle explains why matrix inversion $[A \mid I]$ and LU decomposition $A = LU$ work: once the operations on $A$ are recorded, they can be applied to any number of right-hand side vectors with minimal extra work.
3. **Simultaneous Processing:** Augmenting a matrix with multiple columns $[A \mid b_1 \mid b_2 \mid \dots]$ allows solving multiple systems in parallel with almost no redundant computation.
