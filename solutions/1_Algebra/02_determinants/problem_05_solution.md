# Problem 5: Row Operations

## Question

For

$$
A=
\begin{pmatrix}
1 & 2 & 3 \\
2 & 1 & 0 \\
-1 & 4 & 2 \\
\end{pmatrix}
$$

find $\det A$ by simplifying the matrix with row operations. At each step, indicate whether and how the determinant changes.

---

## Solution

### 1. Effect of Elementary Row Operations on the Determinant

There are three types of elementary row operations:

1. **Row addition/replacement ($R_i \leftarrow R_i + c R_j$ with $i \neq j$):**
   Adding a scalar multiple of one row to another row **leaves the determinant unchanged**:

$$
\det(A_{\mathrm{new}}) = \det A
$$

2. **Row swap ($R_i \leftrightarrow R_j$ with $i \neq j$):**
   Interchanging two rows **changes the sign** of the determinant:

$$
\det(A_{\mathrm{new}}) = -\det A
$$

3. **Row scaling ($R_i \leftarrow c R_i$ with $c \neq 0$):**
   Multiplying a row by a non-zero scalar $c$ **multiplies the determinant by $c$**:

$$
\det(A_{\mathrm{new}}) = c \det A \iff \det A = \frac{1}{c} \det(A_{\mathrm{new}})
$$

The goal is to reduce $A$ to an upper triangular matrix $U$ using row operations while recording any scaling or sign factors.

---

### 2. Step-by-Step Matrix Reduction

Starting matrix:

$$
A =
\begin{pmatrix}
1 & 2 & 3 \\
2 & 1 & 0 \\
-1 & 4 & 2 \\
\end{pmatrix}
$$

#### Step 1: Eliminate Entry $a_{21}$ in Row 2

Operation:

$$
R_2 \leftarrow R_2 - 2 R_1
$$

- **Effect on determinant:** Row replacement leaves the determinant unchanged:

$$
\det A_1 = \det A
$$

- **Row computation:**

$$
\begin{aligned}
R_2 - 2 R_1 &= (2, 1, 0) - 2(1, 2, 3) \\
            &= (2, 1, 0) - (2, 4, 6) \\
            &= (0, -3, -6)
\end{aligned}
$$

Matrix after Step 1:

$$
A_1 =
\begin{pmatrix}
1 & 2 & 3 \\
0 & -3 & -6 \\
-1 & 4 & 2 \\
\end{pmatrix}
$$

---

#### Step 2: Eliminate Entry $a_{31}$ in Row 3

Operation:

$$
R_3 \leftarrow R_3 + R_1
$$

- **Effect on determinant:** Row replacement leaves the determinant unchanged:

$$
\det A_2 = \det A_1 = \det A
$$

- **Row computation:**

$$
\begin{aligned}
R_3 + R_1 &= (-1, 4, 2) + (1, 2, 3) \\
          &= (0, 6, 5)
\end{aligned}
$$

Matrix after Step 2:

$$
A_2 =
\begin{pmatrix}
1 & 2 & 3 \\
0 & -3 & -6 \\
0 & 6 & 5 \\
\end{pmatrix}
$$

---

#### Step 3: Eliminate Entry $a_{32}$ in Row 3

In column 2, the pivot is $a_{22} = -3$. To cancel $a_{32} = 6$, add $2 R_2$ to $R_3$:

Operation:

$$
R_3 \leftarrow R_3 + 2 R_2
$$

- **Effect on determinant:** Row replacement leaves the determinant unchanged:

$$
\det U = \det A_2 = \det A
$$

- **Row computation:**

$$
\begin{aligned}
R_3 + 2 R_2 &= (0, 6, 5) + 2(0, -3, -6) \\
            &= (0, 6, 5) + (0, -6, -12) \\
            &= (0, 0, -7)
\end{aligned}
$$

Matrix after Step 3:

$$
U =
\begin{pmatrix}
1 & 2 & 3 \\
0 & -3 & -6 \\
0 & 0 & -7 \\
\end{pmatrix}
$$

Matrix $U$ is now in upper triangular form.

---

### 3. Computing $\det A$ from the Triangular Form

The determinant of an upper triangular matrix is the product of its diagonal entries:

$$
\det U = (1) \cdot (-3) \cdot (-7) = 21
$$

Since each elementary row operation performed was of type $R_i \leftarrow R_i + c R_j$, no factor or sign change was introduced:

$$
\det A = \det U = 21
$$

---

## Verification and Consistency Checks

1. **Alternative Reduction Involving Row Scaling:**
   From matrix $A_2$:

$$
A_2 =
\begin{pmatrix}
1 & 2 & 3 \\
0 & -3 & -6 \\
0 & 6 & 5 \\
\end{pmatrix}
$$

   Factor out $-3$ from row 2 ($R_2 \leftarrow -\frac{1}{3} R_2$):

$$
\det A_2 = (-3) \cdot \det
\begin{pmatrix}
1 & 2 & 3 \\
0 & 1 & 2 \\
0 & 6 & 5 \\
\end{pmatrix}
$$

   Now eliminate entry $a_{32} = 6$ by $R_3 \leftarrow R_3 - 6 R_2$:

$$
R_3 - 6 R_2 = (0, 6, 5) - 6(0, 1, 2) = (0, 0, -7)
$$

   The resulting upper triangular matrix has determinant $(1)(1)(-7) = -7$.
   Re-applying the scalar factor of $-3$:

$$
\det A = (-3) \cdot (-7) = 21
$$

   This confirms the consistency of the row-scaling rule.

2. **Verification via Sarrus' Rule:**

$$
A =
\begin{pmatrix}
1 & 2 & 3 \\
2 & 1 & 0 \\
-1 & 4 & 2 \\
\end{pmatrix}
$$

   - Downward diagonals:
     - $(1) \cdot (1) \cdot (2) = 2$
     - $(2) \cdot (0) \cdot (-1) = 0$
     - $(3) \cdot (2) \cdot (4) = 24$
     - Sum: $S_1 = 2 + 0 + 24 = 26$

   - Upward diagonals:
     - $(-1) \cdot (1) \cdot (3) = -3$
     - $(4) \cdot (0) \cdot (1) = 0$
     - $(2) \cdot (2) \cdot (2) = 8$
     - Sum: $S_2 = -3 + 0 + 8 = 5$

   Subtracting:

$$
\det A = S_1 - S_2 = 26 - 5 = 21
$$

3. **Verification via Laplace Expansion along Row 2:**
   Row 2 contains a zero ($a_{23} = 0$):

$$
\begin{aligned}
\det A &= -2 \cdot \det
\begin{pmatrix}
2 & 3 \\
4 & 2 \\
\end{pmatrix}
+ 1 \cdot \det
\begin{pmatrix}
1 & 3 \\
-1 & 2 \\
\end{pmatrix}
- 0 \\
&= -2(4 - 12) + 1(2 - (-3)) \\
&= -2(-8) + 1(5) \\
&= 16 + 5 \\
&= 21
\end{aligned}
$$

All three independent checks verify $\det A = 21$.

---

## Why This Exercise Matters

- **Algorithmic Standard:** Gaussian elimination combined with determinant tracking is the standard numerical algorithm for computing determinants in arbitrary dimensions.
- **Complexity Advantage:** Direct cofactor expansion requires $\mathcal{O}(n!)$ operations, whereas row reduction requires only $\mathcal{O}(n^3)$ operations.
- **Mental Tracking Discipline:** Demonstrates how row operations must be tracked explicitly: row additions leave the determinant invariant, row swaps flip the sign, and row scalings multiply the determinant.

