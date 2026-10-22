# Problem 3: Swapping Two Rows

## Question

For

$$
A =
\begin{pmatrix}
1 & 2 & 0 \\
0 & 3 & 1 \\
2 & 1 & 1
\end{pmatrix}
$$

compute $\det A$. Then form a matrix $B$ by swapping the first and second rows of $A$.

First predict $\det B$ using a determinant property, and then verify your prediction by calculation.

---

## Solution

### 1. Computation of $\det A$

We evaluate $\det A$ using Sarrus' rule for $3 \times 3$ matrices:

$$
A =
\begin{pmatrix}
1 & 2 & 0 \\
0 & 3 & 1 \\
2 & 1 & 1
\end{pmatrix}
$$

**Downward diagonal products (positive sign):**
- First diagonal: $(1) \cdot (3) \cdot (1) = 3$
- Second diagonal: $(2) \cdot (1) \cdot (2) = 4$
- Third diagonal: $(0) \cdot (0) \cdot (1) = 0$

Sum of downward products:

$$
S_1 = 3 + 4 + 0 = 7
$$

**Upward diagonal products (negative sign):**
- First anti-diagonal: $(2) \cdot (3) \cdot (0) = 0$
- Second anti-diagonal: $(1) \cdot (1) \cdot (1) = 1$
- Third anti-diagonal: $(1) \cdot (0) \cdot (2) = 0$

Sum of upward products:

$$
S_2 = 0 + 1 + 0 = 1
$$

Subtracting the upward sum from the downward sum:

$$
\begin{aligned}
\det A &= S_1 - S_2 \\
       &= 7 - 1 \\
       &= 6
\end{aligned}
$$

---

### 2. Forming Matrix $B$

Swapping row 1 ($$r_1 = (1, 2, 0)$$) and row 2 ($$r_2 = (0, 3, 1)$$) of matrix $A$ yields:

$$
B =
\begin{pmatrix}
0 & 3 & 1 \\
1 & 2 & 0 \\
2 & 1 & 1
\end{pmatrix}
$$

---

### 3. Prediction of $\det B$ via Determinant Property

**Property (Antisymmetry / Alternating Property):**
If two rows (or two columns) of a square matrix are interchanged, the determinant changes sign:

$$
\det B = -\det A
$$

Since matrix $B$ is obtained from $A$ by exactly one row transposition ($R_1 \leftrightarrow R_2$), the prediction is:

$$
\det B = -\det A = -6
$$

---

### 4. Verification of $\det B$ by Calculation

We verify this prediction by computing $\det B$ directly.

**Method A: Sarrus' Rule on $B$:**

- Downward diagonals:
  - $(0) \cdot (2) \cdot (1) = 0$
  - $(3) \cdot (0) \cdot (2) = 0$
  - $(1) \cdot (1) \cdot (1) = 1$
  - Sum: $S_1 = 0 + 0 + 1 = 1$

- Upward diagonals:
  - $(2) \cdot (2) \cdot (1) = 4$
  - $(1) \cdot (0) \cdot (0) = 0$
  - $(1) \cdot (1) \cdot (3) = 3$
  - Sum: $S_2 = 4 + 0 + 3 = 7$

Evaluating the determinant:

$$
\begin{aligned}
\det B &= S_1 - S_2 \\
       &= 1 - 7 \\
       &= -6
\end{aligned}
$$

**Method B: Laplace Expansion along Row 1 of $B$:**

Row 1 of matrix $B$ contains entries $b_{11} = 0$, $b_{12} = 3$, and $b_{13} = 1$:

$$
\det B = b_{11} C_{11} + b_{12} C_{12} + b_{13} C_{13}
$$

where the cofactors are $C_{ij} = (-1)^{i+j} M_{ij}$:

1. **Term for $b_{11} = 0$:**

$$
b_{11} C_{11} = 0 \cdot C_{11} = 0
$$

2. **Term for $b_{12} = 3$:**

$$
C_{12} = (-1)^{1+2} \det
\begin{pmatrix}
1 & 0 \\
2 & 1
\end{pmatrix}
= -1 \cdot [(1)(1) - (0)(2)] = -1(1 - 0) = -1
$$

3. **Term for $b_{13} = 1$:**

$$
C_{13} = (-1)^{1+3} \det
\begin{pmatrix}
1 & 2 \\
2 & 1
\end{pmatrix}
= 1 \cdot [(1)(1) - (2)(2)] = 1(1 - 4) = -3
$$

Combining the terms:

$$
\begin{aligned}
\det B &= 0 \cdot C_{11} + 3 \cdot C_{12} + 1 \cdot C_{13} \\
       &= 0 + 3(-1) + 1(-3) \\
       &= -3 - 3 \\
       &= -6
\end{aligned}
$$

Both calculation methods confirm that $\det B = -6$, exactly matching the theoretical prediction.

---

## Verification and Consistency Checks

1. **Permutation Matrix Representation:**
   The elementary row operation $R_1 \leftrightarrow R_2$ corresponds to left-multiplication by the elementary permutation matrix $P$:

$$
P =
\begin{pmatrix}
0 & 1 & 0 \\
1 & 0 & 0 \\
0 & 0 & 1
\end{pmatrix}
$$

   Computing the determinant of $P$ using Laplace expansion along row 1:

$$
\det P = 0 \cdot C_{11} - 1 \cdot [(1)(1) - (0)(0)] + 0 \cdot C_{13} = -1
$$

   Using the multiplicative property of determinants:

$$
\det B = \det(PA) = \det P \cdot \det A = (-1) \cdot 6 = -6
$$

2. **Invertibility Status:**
   Since $\det B = -6 \neq 0$, matrix $B$ remains invertible. In general, elementary row operations preserve matrix invertibility (rank is unchanged).

---

## Why This Exercise Matters

- **Alternating Multilinearity:** The determinant is an alternating multilinear form. Swapping two arguments reverses orientation, multiplying the volume form by $-1$.
- **Tracking Row Swaps in Gaussian Elimination:** When solving systems or computing determinants via LU/REF decomposition, every row swap incurs a factor of $(-1)$. Keeping rigorous track of swap counts is essential for the correct determinant sign.
- **Identity for Identical Rows:** If a matrix has two identical rows, swapping them leaves the matrix unchanged ($A = B$), implying $\det A = -\det A \implies 2\det A = 0 \implies \det A = 0$.
