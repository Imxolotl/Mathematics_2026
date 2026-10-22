# Problem 2: Determinant of a 3x3 Matrix

## Question

For

$$
A=
\begin{pmatrix}
1 & 2 & -1 \\
0 & 3 & 4 \\
2 & 1 & 5 \\
\end{pmatrix}
$$

compute $\det A$ using Sarrus' rule. Then perform one simple check using a chosen property of the determinant.

---

## Solution

### 1. Sarrus' Rule for a 3x3 Matrix

Sarrus' rule is a geometric calculation scheme valid exclusively for $3 \times 3$ matrices.

For a general matrix

$$
A =
\begin{pmatrix}
a_{11} & a_{12} & a_{13} \\
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33} \\
\end{pmatrix}
$$

the determinant is computed by adding the products of the three downward diagonals (from top-left to bottom-right) and subtracting the products of the three upward diagonals (from bottom-left to top-right):

$$
\det A = (a_{11}a_{22}a_{33} + a_{12}a_{23}a_{31} + a_{13}a_{21}a_{32}) - (a_{31}a_{22}a_{13} + a_{32}a_{23}a_{11} + a_{33}a_{21}a_{12})
$$

---

### 2. Computing Downward and Upward Diagonal Products

For matrix $A$:

$$
A =
\begin{pmatrix}
1 & 2 & -1 \\
0 & 3 & 4 \\
2 & 1 & 5 \\
\end{pmatrix}
$$

**Downward diagonal products (positive sign):**
- First diagonal:
  $(1) \cdot (3) \cdot (5) = 15$
- Second diagonal:
  $(2) \cdot (4) \cdot (2) = 16$
- Third diagonal:
  $(-1) \cdot (0) \cdot (1) = 0$

Sum of downward products:

$$
S_1 = 15 + 16 + 0 = 31
$$

**Upward diagonal products (negative sign):**
- First anti-diagonal:
  $(2) \cdot (3) \cdot (-1) = -6$
- Second anti-diagonal:
  $(1) \cdot (4) \cdot (1) = 4$
- Third anti-diagonal:
  $(5) \cdot (0) \cdot (2) = 0$

Sum of upward products:

$$
S_2 = (-6) + 4 + 0 = -2
$$

---

### 3. Evaluating $\det A$

Subtracting the upward sum from the downward sum:

$$
\begin{aligned}
\det A &= S_1 - S_2 \\
       &= 31 - (-2) \\
       &= 31 + 2 \\
       &= 33
\end{aligned}
$$

---

### 4. Check Using Laplace Expansion (Cofactor Expansion)

To check the result quickly without repeating Sarrus' calculation, we expand along the **first column** using Laplace's theorem. Column 1 is particularly efficient because its second entry is zero ($a_{21} = 0$):

$$
\det A = a_{11} C_{11} + a_{21} C_{21} + a_{31} C_{31}
$$

where the cofactor is $C_{ij} = (-1)^{i+j} M_{ij}$, with $M_{ij}$ denoting the subdeterminant obtained by deleting row $i$ and column $j$.

1. **Term for $a_{11} = 1$:**

$$
C_{11} = (-1)^{1+1} \det
\begin{pmatrix}
3 & 4 \\
1 & 5 \\
\end{pmatrix}
= 1 \cdot [(3)(5) - (4)(1)] = 15 - 4 = 11
$$

2. **Term for $a_{21} = 0$:**

$$
a_{21} C_{21} = 0 \cdot C_{21} = 0
$$

3. **Term for $a_{31} = 2$:**

$$
C_{31} = (-1)^{3+1} \det
\begin{pmatrix}
2 & -1 \\
3 & 4 \\
\end{pmatrix}
= 1 \cdot [(2)(4) - (-1)(3)] = 8 - (-3) = 11
$$

Combining the terms:

$$
\begin{aligned}
\det A &= 1 \cdot 11 + 0 + 2 \cdot 11 \\
       &= 11 + 22 \\
       &= 33
\end{aligned}
$$

Both methods yield exactly $33$, confirming the calculation.

---

## Verification and Consistency Checks

1. **Check using Row Operations:**
   Subtract $2 R_1$ from $R_3$:

$$
R_3 \leftarrow R_3 - 2 R_1
$$

   Row 3 becomes $(2 - 2(1), 1 - 2(2), 5 - 2(-1)) = (0, -3, 7)$.
   Since adding a multiple of one row to another preserves the determinant:

$$
\det A = \det
\begin{pmatrix}
1 & 2 & -1 \\
0 & 3 & 4 \\
0 & -3 & 7 \\
\end{pmatrix}
$$

   Adding $R_2$ to $R_3$:

$$
R_3 \leftarrow R_3 + R_2
$$

   Row 3 becomes $(0, 0, 11)$. The matrix is now upper triangular:

$$
\det A = \det
\begin{pmatrix}
1 & 2 & -1 \\
0 & 3 & 4 \\
0 & 0 & 11 \\
\end{pmatrix}
= 1 \cdot 3 \cdot 11 = 33
$$

2. **Invertibility Status:**
   Since $\det A = 33 \neq 0$, the matrix $A$ is invertible, and its row/column vectors form a basis of $\mathbb{R}^3$.

---

## Why This Exercise Matters

- **Mastery of Sarrus' Rule:** Provides a fast, direct algorithmic method for $3 \times 3$ matrices without requiring cofactor signs.
- **Limitation Awareness:** Sarrus' rule works **only** for $3 \times 3$ matrices; it fails for $4 \times 4$ and larger matrices ($4! = 24$ permutations, whereas the diagonal trick would only produce 8 terms).
- **Verification Strategy:** Demonstrates how choosing a row or column with zero entries makes Laplace expansion much faster than blindly recalculating from scratch.

