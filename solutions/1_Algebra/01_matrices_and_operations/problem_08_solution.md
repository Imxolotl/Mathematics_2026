# Problem 8: Row Operations and Their Reversibility

## Question

For

$$
A = \begin{pmatrix}
1 & 2 & -1 \\
2 & 4 & 1 \\
-1 & 1 & 3
\end{pmatrix}
$$

perform, in order:

1. $R_2 \leftarrow R_2 - 2R_1$,
2. $R_3 \leftarrow R_3 + R_1$,
3. interchange $R_2$ and $R_3$.

Write the matrix after each step. Then, for each of the three operations, state an operation that reverses it.

---

## Key Concept — Elementary Row Operations (EROs)

An **elementary row operation** is an operation performed on the rows of a matrix. There are three types:

1. **Row addition / replacement:** Add a multiple of one row to another row: $R_i \leftarrow R_i + c R_j$ ($j \neq i$).
2. **Row swap / interchange:** Swap two rows: $R_i \leftrightarrow R_j$.
3. **Row scaling:** Multiply a row by a non-zero scalar: $R_i \leftarrow c R_i$ ($c \neq 0$).

A fundamental principle of row operations is that **every operation is reversible**: it never loses information. Performing an operation and immediately following it with its inverse restores the matrix to its previous state.

---

## Step 1 — Operation: $R_2 \leftarrow R_2 - 2R_1$

We replace row 2 by row 2 minus twice row 1.

### Row calculation

- Current row 2: $(2, 4, 1)$
- Twice row 1: $2 \cdot (1, 2, -1) = (2, 4, -2)$
- Subtracting:

$$
(2 - 2, \quad 4 - 4, \quad 1 - (-2)) = (0, \quad 0, \quad 3)
$$

### Resulting Matrix $A_1$

$$
A_1 = \begin{pmatrix}
1 & 2 & -1 \\
0 & 0 & 3 \\
-1 & 1 & 3
\end{pmatrix}
$$

### Reversing Operation

To undo subtracting $2R_1$, we **add $2R_1$ back to row 2**:

$$
R_2 \leftarrow R_2 + 2R_1
$$

Checking on $A_1$:

$$
(0, 0, 3) + 2 \cdot (1, 2, -1) = (0 + 2, 0 + 4, 3 - 2) = (2, 4, 1)
$$

This restores the original row 2. ✅

---

## Step 2 — Operation: $R_3 \leftarrow R_3 + R_1$

We apply this to the current matrix $A_1$. Row 3 is replaced by the sum of row 3 and row 1.

### Row calculation

- Current row 3: $(-1, 1, 3)$
- Row 1: $(1, 2, -1)$
- Adding:

$$
(-1 + 1, \quad 1 + 2, \quad 3 + (-1)) = (0, \quad 3, \quad 2)
$$

### Resulting Matrix $A_2$

$$
A_2 = \begin{pmatrix}
1 & 2 & -1 \\
0 & 0 & 3 \\
0 & 3 & 2
\end{pmatrix}
$$

### Reversing Operation

To undo adding $R_1$, we **subtract $R_1$ from row 3**:

$$
R_3 \leftarrow R_3 - R_1
$$

Checking on $A_2$:

$$
(0, 3, 2) - (1, 2, -1) = (0 - 1, 3 - 2, 2 - (-1)) = (-1, 1, 3)
$$

This restores row 3 of $A_1$. ✅

---

## Step 3 — Operation: Interchange $R_2$ and $R_3$

We swap rows 2 and 3 of matrix $A_2$.

### Resulting Matrix $A_3$

$$
A_3 = \begin{pmatrix}
1 & 2 & -1 \\
0 & 3 & 2 \\
0 & 0 & 3
\end{pmatrix}
$$

Notice that $A_3$ is now in **upper triangular form** (and row echelon form), with non-zero pivots $1, 3, 3$ along the main diagonal.

### Reversing Operation

Interchanging rows is **self-reversing**. To undo the swap, we **interchange row 2 and row 3 again**:

$$
R_2 \leftrightarrow R_3
$$

Performing this swap on $A_3$ immediately restores $A_2$. ✅

---

## Summary of Operations and Inverses

| Step | Forward Operation | Target Matrix | Inverse (Reversing) Operation | Description of Reversal |
|:---:|:---|:---:|:---|:---|
| 1 | $R_2 \leftarrow R_2 - 2R_1$ | $A_1$ | $R_2 \leftarrow R_2 + 2R_1$ | Add 2 times row 1 back to row 2 |
| 2 | $R_3 \leftarrow R_3 + R_1$ | $A_2$ | $R_3 \leftarrow R_3 - R_1$ | Subtract row 1 from row 3 |
| 3 | $R_2 \leftrightarrow R_3$ | $A_3$ | $R_2 \leftrightarrow R_3$ | Swap row 2 and row 3 again |

---

## Reversing the Entire Sequence: From $A_3$ Back to $A$

To reverse a sequence of operations, we must apply their inverses in **reverse order**:

1. **Step 1:** Undo the swap by applying $R_2 \leftrightarrow R_3$ to $A_3$:

$$
\begin{pmatrix}
1 & 2 & -1 \\
0 & 3 & 2 \\
0 & 0 & 3
\end{pmatrix}
\xrightarrow{R_2 \leftrightarrow R_3}
\begin{pmatrix}
1 & 2 & -1 \\
0 & 0 & 3 \\
0 & 3 & 2
\end{pmatrix}
= A_2
$$

2. **Step 2:** Undo row 3 replacement by applying $R_3 \leftarrow R_3 - R_1$ to $A_2$:

$$
\begin{pmatrix}
1 & 2 & -1 \\
0 & 0 & 3 \\
0 & 3 & 2
\end{pmatrix}
\xrightarrow{R_3 \leftarrow R_3 - R_1}
\begin{pmatrix}
1 & 2 & -1 \\
0 & 0 & 3 \\
-1 & 1 & 3
\end{pmatrix}
= A_1
$$

3. **Step 3:** Undo row 2 replacement by applying $R_2 \leftarrow R_2 + 2R_1$ to $A_1$:

$$
\begin{pmatrix}
1 & 2 & -1 \\
0 & 0 & 3 \\
-1 & 1 & 3
\end{pmatrix}
\xrightarrow{R_2 \leftarrow R_2 + 2R_1}
\begin{pmatrix}
1 & 2 & -1 \\
2 & 4 & 1 \\
-1 & 1 & 3
\end{pmatrix}
= A
$$

The starting matrix $A$ is fully recovered. ✅

---

## Deeper Insight: Elementary Matrices

Each elementary row operation corresponds to multiplying on the left by an elementary matrix $E$:

- **Operation 1 ($R_2 \leftarrow R_2 - 2R_1$):**

$$
E_1 = \begin{pmatrix} 1 & 0 & 0 \\ -2 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix}, \qquad
E_1^{-1} = \begin{pmatrix} 1 & 0 & 0 \\ 2 & 1 & 0 \\ 0 & 0 & 1 \end{pmatrix}
$$

- **Operation 2 ($R_3 \leftarrow R_3 + R_1$):**

$$
E_2 = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 1 & 0 & 1 \end{pmatrix}, \qquad
E_2^{-1} = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ -1 & 0 & 1 \end{pmatrix}
$$

- **Operation 3 ($R_2 \leftrightarrow R_3$):**

$$
E_3 = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 0 & 1 \\ 0 & 1 & 0 \end{pmatrix}, \qquad
E_3^{-1} = \begin{pmatrix} 1 & 0 & 0 \\ 0 & 0 & 1 \\ 0 & 1 & 0 \end{pmatrix}
$$

The final matrix is:

$$
A_3 = E_3 E_2 E_1 A
$$

To recover $A$, we invert the product by reversing order:

$$
A = E_1^{-1} E_2^{-1} E_3^{-1} A_3
$$

---

## Verification: Determinant Tracking

Row operations affect the determinant in specific ways:
- Adding a multiple of one row to another does not change the determinant: $\det(A_1) = \det(A)$, $\det(A_2) = \det(A_1)$.
- Swapping two rows multiplies the determinant by $-1$: $\det(A_3) = -\det(A_2) = -\det(A)$.

Because $A_3$ is upper triangular, its determinant is the product of its diagonal entries:

$$
\det(A_3) = 1 \cdot 3 \cdot 3 = 9
$$

Therefore:

$$
\det(A) = -\det(A_3) = -9
$$

Direct expansion of $A$ along row 1:

$$
\det(A) = 1(12 - 1) - 2(6 + 1) - 1(2 + 4) = 11 - 14 - 6 = -9
$$

The values match. ✅

---

## Why This Exercise Matters

- **Engine of Gaussian Elimination:** Row replacement and row swaps are the systematic tools used to convert any linear system into upper-triangular echelon form.
- **Equivalent Systems:** Because row operations are invertible, solving the transformed triangular system produces the exact same solutions as the original system.
- **Matrix Inversion:** The product of the elementary matrices used in Gauss-Jordan elimination directly builds the matrix inverse $A^{-1}$.
