# Problem 5: A 3x3 Matrix

## Question

Use Gauss–Jordan elimination to find the inverse of

$$
A=
\begin{pmatrix}
1 & 1 & 0 \\
0 & 1 & 1 \\
1 & 0 & 1
\end{pmatrix}.
$$

Check the result by multiplication.

---

## Solution

### 1. Setting Up the Augmented Matrix

To find $A^{-1}$ using Gauss–Jordan elimination, we form the augmented matrix $[A \mid I_3]$ by adjoining the $3 \times 3$ identity matrix to the right of $A$:

$$
\begin{pmatrix}
1 & 1 & 0 & \mid & 1 & 0 & 0 \\
0 & 1 & 1 & \mid & 0 & 1 & 0 \\
1 & 0 & 1 & \mid & 0 & 0 & 1
\end{pmatrix}
$$

Our goal is to apply elementary row operations until the left $3 \times 3$ block becomes $I_3$.

---

### 2. Forward Elimination (Row Echelon Form)

#### Step 1: Eliminate Entry in Row 3, Column 1

The pivot in column 1 is already $1$ (entry $a_{11} = 1$). Entry $a_{21}$ is already $0$.
Row operation: subtract row 1 from row 3:

$$
R_3 \leftarrow R_3 - R_1
$$

Computing the new row 3:
- Left block: $(1 - 1, 0 - 1, 1 - 0) = (0, -1, 1)$
- Right block: $(0 - 1, 0 - 0, 1 - 0) = (-1, 0, 1)$

The augmented matrix becomes:

$$
\begin{pmatrix}
1 & 1 & 0 & \mid & 1 & 0 & 0 \\
0 & 1 & 1 & \mid & 0 & 1 & 0 \\
0 & -1 & 1 & \mid & -1 & 0 & 1
\end{pmatrix}
$$

#### Step 2: Eliminate Entry in Row 3, Column 2

The pivot in column 2 is already $1$ (entry $a_{22} = 1$).
Row operation: add row 2 to row 3:

$$
R_3 \leftarrow R_3 + R_2
$$

Computing the new row 3:
- Left block: $(0 + 0, -1 + 1, 1 + 1) = (0, 0, 2)$
- Right block: $(-1 + 0, 0 + 1, 1 + 0) = (-1, 1, 1)$

The augmented matrix becomes:

$$
\begin{pmatrix}
1 & 1 & 0 & \mid & 1 & 0 & 0 \\
0 & 1 & 1 & \mid & 0 & 1 & 0 \\
0 & 0 & 2 & \mid & -1 & 1 & 1
\end{pmatrix}
$$

The left block is now in upper triangular form.

---

### 3. Backward Elimination (Reduced Row Echelon Form)

#### Step 3: Scale Row 3 to Make the Third Pivot Equal to $1$

Row operation: multiply row 3 by $\frac{1}{2}$:

$$
R_3 \leftarrow \frac{1}{2} R_3
$$

Computing the new row 3:
- Left block: $\frac{1}{2}(0, 0, 2) = (0, 0, 1)$
- Right block: $\frac{1}{2}(-1, 1, 1) = \left(-\frac{1}{2}, \frac{1}{2}, \frac{1}{2}\right)$

The augmented matrix becomes:

$$
\begin{pmatrix}
1 & 1 & 0 & \mid & 1 & 0 & 0 \\
0 & 1 & 1 & \mid & 0 & 1 & 0 \\
0 & 0 & 1 & \mid & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2}
\end{pmatrix}
$$

#### Step 4: Eliminate Entry in Row 2, Column 3

Row operation: subtract row 3 from row 2:

$$
R_2 \leftarrow R_2 - R_3
$$

Computing the new row 2:
- Left block: $(0 - 0, 1 - 0, 1 - 1) = (0, 1, 0)$
- Right block: $\left(0 - \left(-\frac{1}{2}\right), 1 - \frac{1}{2}, 0 - \frac{1}{2}\right) = \left(\frac{1}{2}, \frac{1}{2}, -\frac{1}{2}\right)$

The augmented matrix becomes:

$$
\begin{pmatrix}
1 & 1 & 0 & \mid & 1 & 0 & 0 \\
0 & 1 & 0 & \mid & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\
0 & 0 & 1 & \mid & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2}
\end{pmatrix}
$$

#### Step 5: Eliminate Entry in Row 1, Column 2

Row operation: subtract row 2 from row 1:

$$
R_1 \leftarrow R_1 - R_2
$$

Computing the new row 1:
- Left block: $(1 - 0, 1 - 1, 0 - 0) = (1, 0, 0)$
- Right block: $\left(1 - \frac{1}{2}, 0 - \frac{1}{2}, 0 - \left(-\frac{1}{2}\right)\right) = \left(\frac{1}{2}, -\frac{1}{2}, \frac{1}{2}\right)$

The augmented matrix reaches reduced row echelon form (RREF):

$$
\begin{pmatrix}
1 & 0 & 0 & \mid & \frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\
0 & 1 & 0 & \mid & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\
0 & 0 & 1 & \mid & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2}
\end{pmatrix}
$$

---

### 4. The Inverse Matrix

The left block is $I_3$, so the right block is $A^{-1}$:

$$
A^{-1} =
\begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\
\frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\
-\frac{1}{2} & \frac{1}{2} & \frac{1}{2}
\end{pmatrix}
= \frac{1}{2}
\begin{pmatrix}
1 & -1 & 1 \\
1 & 1 & -1 \\
-1 & 1 & 1
\end{pmatrix}
$$

---

### 5. Check by Multiplication

We verify the result by computing the product $A A^{-1}$. Factoring out $\frac{1}{2}$:

$$
A A^{-1} = \frac{1}{2}
\begin{pmatrix}
1 & 1 & 0 \\
0 & 1 & 1 \\
1 & 0 & 1
\end{pmatrix}
\begin{pmatrix}
1 & -1 & 1 \\
1 & 1 & -1 \\
-1 & 1 & 1
\end{pmatrix}
$$

Evaluating each row · column dot product:
- Row 1: $(1)(1) + (1)(1) + (0)(-1) = 2$, $(1)(-1) + (1)(1) + (0)(1) = 0$, $(1)(1) + (1)(-1) + (0)(1) = 0$
- Row 2: $(0)(1) + (1)(1) + (1)(-1) = 0$, $(0)(-1) + (1)(1) + (1)(1) = 2$, $(0)(1) + (1)(-1) + (1)(1) = 0$
- Row 3: $(1)(1) + (0)(1) + (1)(-1) = 0$, $(1)(-1) + (0)(1) + (1)(1) = 0$, $(1)(1) + (0)(-1) + (1)(1) = 2$

Multiplying the resulting matrix by the scalar $\frac{1}{2}$:

$$
A A^{-1} = \frac{1}{2}
\begin{pmatrix}
2 & 0 & 0 \\
0 & 2 & 0 \\
0 & 0 & 2
\end{pmatrix}
= \begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
= I_3
$$

The product is the $3 \times 3$ identity matrix, confirming that $A^{-1}$ is correct.

---

## Verification and Consistency Checks

### Check 1: Left-Multiplication ($A^{-1} A$)

Computing the reverse product:

$$
A^{-1} A = \frac{1}{2}
\begin{pmatrix}
1 & -1 & 1 \\
1 & 1 & -1 \\
-1 & 1 & 1
\end{pmatrix}
\begin{pmatrix}
1 & 1 & 0 \\
0 & 1 & 1 \\
1 & 0 & 1
\end{pmatrix}
$$

Evaluating entries:
- Row 1: $(1+0+1, 1-1+0, 0-1+1) = (2, 0, 0)$
- Row 2: $(1+0-1, 1+1+0, 0+1-1) = (0, 2, 0)$
- Row 3: $(-1+0+1, -1+1+0, 0+1+1) = (0, 0, 2)$

$$
A^{-1} A = \frac{1}{2}
\begin{pmatrix}
2 & 0 & 0 \\
0 & 2 & 0 \\
0 & 0 & 2
\end{pmatrix}
= I_3
$$

### Check 2: Determinant Consistency

Evaluating $\det A$ using Sarrus' rule:

$$
\det A = (1 \cdot 1 \cdot 1 + 1 \cdot 1 \cdot 1 + 0 \cdot 0 \cdot 0) - (1 \cdot 1 \cdot 0 + 0 \cdot 1 \cdot 1 + 1 \cdot 0 \cdot 1) = 2 - 0 = 2
$$

Evaluating $\det(A^{-1})$:

$$
\det(A^{-1}) = \left(\frac{1}{2}\right)^3 \det
\begin{pmatrix}
1 & -1 & 1 \\
1 & 1 & -1 \\
-1 & 1 & 1
\end{pmatrix}
= \frac{1}{8} \cdot 4 = \frac{1}{2}
$$

Since $\det(A^{-1}) = \frac{1}{\det A} = \frac{1}{2}$, this provides another consistency check.

---

## Why This Exercise Matters

- **Mastering the Standard Algorithm for $3 \times 3$ Matrices:** Gauss–Jordan elimination avoids the calculation of $9$ separate $2 \times 2$ cofactors required by Cramer's adjugate rule.
- **Systematic Two-Phase Strategy:** Highlights the division into forward elimination (creating lower triangular zeros) and backward elimination (clearing upper triangular entries), which minimizes arithmetic mistakes.
- **Fraction Management:** Factoring out a common denominator (such as $\frac{1}{2}$) keeps matrix multiplication clear and reduces fractional bookkeeping errors during verification.
