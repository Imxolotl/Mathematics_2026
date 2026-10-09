# Problem 2: Addition and Scalar Multiplication

## Question

For

$$
A =
\begin{pmatrix}
1 & 2 \\
-1 & 3 \\
\end{pmatrix},\qquad B =
\begin{pmatrix}
4 & -2 \\
0 & 5 \\
\end{pmatrix}
$$

compute

$$
A+B, \qquad A-B, \qquad 3A-2B.
$$

Explain why matrix addition is possible only for matrices of the same size.

---

## Solution

### 1. Dimension Compatibility

Before performing addition or subtraction, the dimensions of the matrices must be compared:
- Matrix $A$ has 2 rows and 2 columns: size $2 \times 2$.
- Matrix $B$ has 2 rows and 2 columns: size $2 \times 2$.

Because both matrices share identical dimensions ($2 \times 2$), addition $A+B$, subtraction $A-B$, and linear combinations such as $3A-2B$ are well-defined. The resulting matrix in each case will also have size $2 \times 2$.

---

### 2. Computation of $A + B$

Matrix addition is performed entry-by-entry. For two matrices $A$ and $B$ of the same size, the entries of the sum $C = A+B$ are given by:

$$
c_{ij} = a_{ij} + b_{ij}
$$

Evaluating each entry:
- Row 1, Column 1: $c_{11} = a_{11} + b_{11} = 1 + 4 = 5$
- Row 1, Column 2: $c_{12} = a_{12} + b_{12} = 2 + (-2) = 0$
- Row 2, Column 1: $c_{21} = a_{21} + b_{21} = -1 + 0 = -1$
- Row 2, Column 2: $c_{22} = a_{22} + b_{22} = 3 + 5 = 8$

Written as an aligned derivation:

$$
\begin{aligned}
A + B &=
\begin{pmatrix}
1 & 2 \\
-1 & 3 \\
\end{pmatrix} +
\begin{pmatrix}
4 & -2 \\
0 & 5 \\
\end{pmatrix} \\
&=
\begin{pmatrix}
1 + 4 & 2 + (-2) \\
-1 + 0 & 3 + 5 \\
\end{pmatrix} \\
&=
\begin{pmatrix}
5 & 0 \\
-1 & 8 \\
\end{pmatrix}
\end{aligned}
$$

---

### 3. Computation of $A - B$

Matrix subtraction is also performed entry-by-entry by subtracting each corresponding entry of $B$ from $A$:

$$
(A - B)_{ij} = a_{ij} - b_{ij}
$$

Evaluating each entry:
- Row 1, Column 1: $1 - 4 = -3$
- Row 1, Column 2: $2 - (-2) = 2 + 2 = 4$
- Row 2, Column 1: $-1 - 0 = -1$
- Row 2, Column 2: $3 - 5 = -2$

Written as an aligned derivation:

$$
\begin{aligned}
A - B &=
\begin{pmatrix}
1 & 2 \\
-1 & 3 \\
\end{pmatrix} -
\begin{pmatrix}
4 & -2 \\
0 & 5 \\
\end{pmatrix} \\
&=
\begin{pmatrix}
1 - 4 & 2 - (-2) \\
-1 - 0 & 3 - 5 \\
\end{pmatrix} \\
&=
\begin{pmatrix}
-3 & 4 \\
-1 & -2 \\
\end{pmatrix}
\end{aligned}
$$

---

### 4. Computation of $3A - 2B$

This expression is a linear combination of matrices involving scalar multiplication followed by subtraction.

Scalar multiplication scales every entry of a matrix by that scalar:

$$
(kA)_{ij} = k \cdot a_{ij}
$$

First, scale matrix $A$ by $3$:

$$
\begin{aligned}
3A &= 3
\begin{pmatrix}
1 & 2 \\
-1 & 3 \\
\end{pmatrix} \\
&=
\begin{pmatrix}
3 \cdot 1 & 3 \cdot 2 \\
3 \cdot (-1) & 3 \cdot 3 \\
\end{pmatrix} \\
&=
\begin{pmatrix}
3 & 6 \\
-3 & 9 \\
\end{pmatrix}
\end{aligned}
$$

Next, scale matrix $B$ by $2$:

$$
\begin{aligned}
2B &= 2
\begin{pmatrix}
4 & -2 \\
0 & 5 \\
\end{pmatrix} \\
&=
\begin{pmatrix}
2 \cdot 4 & 2 \cdot (-2) \\
2 \cdot 0 & 2 \cdot 5 \\
\end{pmatrix} \\
&=
\begin{pmatrix}
8 & -4 \\
0 & 10 \\
\end{pmatrix}
\end{aligned}
$$

Subtract $2B$ from $3A$ entry-by-entry:
- Row 1, Column 1: $3 - 8 = -5$
- Row 1, Column 2: $6 - (-4) = 6 + 4 = 10$
- Row 2, Column 1: $-3 - 0 = -3$
- Row 2, Column 2: $9 - 10 = -1$

Putting the steps together:

$$
\begin{aligned}
3A - 2B &=
\begin{pmatrix}
3 & 6 \\
-3 & 9 \\
\end{pmatrix} -
\begin{pmatrix}
8 & -4 \\
0 & 10 \\
\end{pmatrix} \\
&=
\begin{pmatrix}
3 - 8 & 6 - (-4) \\
-3 - 0 & 9 - 10 \\
\end{pmatrix} \\
&=
\begin{pmatrix}
-5 & 10 \\
-3 & -1 \\
\end{pmatrix}
\end{aligned}
$$

---

### 5. Why Matrix Addition Requires Identical Sizes

Matrix addition is defined strictly as an entry-by-entry operation. Two complementary perspectives explain why equal dimensions are required:

#### Arithmetic Perspective (Element-Wise Pairing)

By definition, the sum of two matrices $A$ and $B$ is computed entry-by-entry for every row index $i$ and column index $j$:

$$
(A + B)_{ij} = a_{ij} + b_{ij}
$$

This rule requires a strict one-to-one pairing between every entry of $A$ and the corresponding entry of $B$:
- If matrix $A$ has size $m \times n$ and matrix $B$ has size $p \times q$ with $m \neq p$ or $n \neq q$, certain positions $(i, j)$ exist in one matrix but do not exist in the other.
- For any unmatched position, the addition has no corresponding entry to add.
- One cannot leave blank positions in a matrix, nor can one arbitrarily insert zeros to pad the smaller matrix, because changing the entries fundamentally alters the matrix and the linear transformation it represents.

#### Geometric and Algebraic Perspective (Linear Transformations)

A matrix of size $m \times n$ represents a linear transformation from $\mathbb{R}^n$ to $\mathbb{R}^m$. Matrix addition corresponds to the pointwise sum of two transformations:

$$
(T_A + T_B)(v) = T_A(v) + T_B(v)
$$

For this sum to be mathematically defined:
- Both transformations must share the same domain $\mathbb{R}^n$ (equal number of columns), so that any input vector $v$ can be evaluated by both mappings.
- Both transformations must share the same codomain $\mathbb{R}^m$ (equal number of rows), so that the resulting output vectors $T_A(v)$ and $T_B(v)$ exist in the same vector space and can be added together.

Because vectors from different Euclidean spaces (such as $\mathbb{R}^2$ and $\mathbb{R}^3$) cannot be added, two matrices can be added if and only if both their row counts and their column counts are identical.

---

## Verification and Consistency Checks

1. **Inverse operation check:**
   Subtracting $B$ from the computed sum $A + B$ must recover matrix $A$:

$$
\begin{aligned}
(A + B) - B &=
\begin{pmatrix}
5 & 0 \\
-1 & 8 \\
\end{pmatrix} -
\begin{pmatrix}
4 & -2 \\
0 & 5 \\
\end{pmatrix} \\
&=
\begin{pmatrix}
5 - 4 & 0 - (-2) \\
-1 - 0 & 8 - 5 \\
\end{pmatrix} \\
&=
\begin{pmatrix}
1 & 2 \\
-1 & 3 \\
\end{pmatrix} \\
&= A
\end{aligned}
$$

2. **Commutativity check:**
   Matrix addition is commutative ($A + B = B + A$):

$$
\begin{aligned}
B + A &=
\begin{pmatrix}
4 & -2 \\
0 & 5 \\
\end{pmatrix} +
\begin{pmatrix}
1 & 2 \\
-1 & 3 \\
\end{pmatrix} \\
&=
\begin{pmatrix}
4 + 1 & -2 + 2 \\
0 + (-1) & 5 + 3 \\
\end{pmatrix} \\
&=
\begin{pmatrix}
5 & 0 \\
-1 & 8 \\
\end{pmatrix} \\
&= A + B
\end{aligned}
$$

3. **Linear combination consistency check:**
   Adding $2B$ back to $(3A - 2B)$ must yield $3A$:

$$
\begin{aligned}
(3A - 2B) + 2B &=
\begin{pmatrix}
-5 & 10 \\
-3 & -1 \\
\end{pmatrix} +
\begin{pmatrix}
8 & -4 \\
0 & 10 \\
\end{pmatrix} \\
&=
\begin{pmatrix}
-5 + 8 & 10 + (-4) \\
-3 + 0 & -1 + 10 \\
\end{pmatrix} \\
&=
\begin{pmatrix}
3 & 6 \\
-3 & 9 \\
\end{pmatrix} \\
&= 3A
\end{aligned}
$$

4. **Dimension consistency:**
   - Both input matrices have size $2 \times 2$.
   - The results $A+B$, $A-B$, and $3A-2B$ are each $2 \times 2$ matrices with $2 \cdot 2 = 4$ entries.

---

## Why This Exercise Matters

- **Reinforces entry-by-entry mechanics:** Matrix addition and scalar multiplication operate purely component-wise, directly paralleling vector addition and vector scaling.
- **Emphasizes dimension compatibility:** Checking that matrix dimensions match before computing is a vital prerequisite for all linear algebra operations.
- **Builds toward vector spaces:** Matrices of a fixed size $m \times n$ form a vector space under addition and scalar multiplication, inheriting core algebraic properties such as commutativity, associativity, and distributivity.
