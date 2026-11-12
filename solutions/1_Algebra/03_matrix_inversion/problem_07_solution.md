# Problem 7: Inverse of a Product

## Question

For

$$
A=
\begin{pmatrix}
1 & 1 \\
0 & 1
\end{pmatrix},\qquad B=
\begin{pmatrix}
2 & 0 \\
0 & 3
\end{pmatrix}
$$

compute $(AB)^{-1}$ and $B^{-1}A^{-1}$. Check that the results are the same and explain the meaning of the reversed order.

---

## Solution

### 1. Inversion of a Matrix Product Property

For any two invertible matrices $A$ and $B$ of the same size, the inverse of their product is the product of their inverses in **reversed order**:

$$
(AB)^{-1} = B^{-1}A^{-1}
$$

To verify this property algebraically from the definition of the inverse, multiply $(AB)$ by $(B^{-1}A^{-1})$:

$$
(AB)(B^{-1}A^{-1}) = A(B B^{-1})A^{-1} = A(I)A^{-1} = AA^{-1} = I
$$

Similarly, for multiplication in the other order:

$$
(B^{-1}A^{-1})(AB) = B^{-1}(A^{-1}A)B = B^{-1}(I)B = B^{-1}B = I
$$

Because $B^{-1}A^{-1}$ yields the identity when multiplied by $AB$ from either side, it is by definition $(AB)^{-1}$.

---

### 2. Method 1: Computing $(AB)^{-1}$ Directly

#### Step 1: Compute the Matrix Product $AB$

We multiply $A$ on the left and $B$ on the right:

$$
AB =
\begin{pmatrix}
1 & 1 \\
0 & 1
\end{pmatrix}
\begin{pmatrix}
2 & 0 \\
0 & 3
\end{pmatrix}
$$

Computing each entry:
- Row 1 · Column 1: $(1)(2) + (1)(0) = 2 + 0 = 2$
- Row 1 · Column 2: $(1)(0) + (1)(3) = 0 + 3 = 3$
- Row 2 · Column 1: $(0)(2) + (1)(0) = 0 + 0 = 0$
- Row 2 · Column 2: $(0)(0) + (1)(3) = 0 + 3 = 3$

$$
AB =
\begin{pmatrix}
2 & 3 \\
0 & 3
\end{pmatrix}
$$

#### Step 2: Compute the Inverse of $AB$

Matrix $AB$ is upper triangular. Its determinant is:

$$
\det(AB) = (2)(3) - (3)(0) = 6
$$

Applying the $2 \times 2$ inverse formula to $AB$:

$$
(AB)^{-1} = \frac{1}{6}
\begin{pmatrix}
3 & -3 \\
0 & 2
\end{pmatrix}
= \begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} \\
0 & \frac{1}{3}
\end{pmatrix}
$$

---

### 3. Method 2: Computing $B^{-1}A^{-1}$

#### Step 1: Invert Matrix $A$

Matrix $A$ is given by:

$$
A =
\begin{pmatrix}
1 & 1 \\
0 & 1
\end{pmatrix}
$$

Its determinant is $\det A = (1)(1) - (1)(0) = 1$. Applying the $2 \times 2$ inverse formula:

$$
A^{-1} = \frac{1}{1}
\begin{pmatrix}
1 & -1 \\
0 & 1
\end{pmatrix}
= \begin{pmatrix}
1 & -1 \\
0 & 1
\end{pmatrix}
$$

#### Step 2: Invert Matrix $B$

Matrix $B$ is diagonal:

$$
B =
\begin{pmatrix}
2 & 0 \\
0 & 3
\end{pmatrix}
$$

Because $B$ is diagonal with non-zero diagonal entries, its inverse is obtained by taking the reciprocal of each diagonal entry:

$$
B^{-1} =
\begin{pmatrix}
\frac{1}{2} & 0 \\
0 & \frac{1}{3}
\end{pmatrix}
$$

#### Step 3: Compute the Product $B^{-1}A^{-1}$

Multiplying $B^{-1}$ on the left and $A^{-1}$ on the right:

$$
B^{-1}A^{-1} =
\begin{pmatrix}
\frac{1}{2} & 0 \\
0 & \frac{1}{3}
\end{pmatrix}
\begin{pmatrix}
1 & -1 \\
0 & 1
\end{pmatrix}
$$

Computing each entry:
- Row 1 · Column 1: $\left(\frac{1}{2}\right)(1) + (0)(0) = \frac{1}{2}$
- Row 1 · Column 2: $\left(\frac{1}{2}\right)(-1) + (0)(1) = -\frac{1}{2}$
- Row 2 · Column 1: $(0)(1) + \left(\frac{1}{3}\right)(0) = 0$
- Row 2 · Column 2: $(0)(-1) + \left(\frac{1}{3}\right)(1) = \frac{1}{3}$

$$
B^{-1}A^{-1} =
\begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} \\
0 & \frac{1}{3}
\end{pmatrix}
$$

---

### 4. Comparison and Explanation of the Reversed Order

Comparing the two results:

$$
(AB)^{-1} =
\begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} \\
0 & \frac{1}{3}
\end{pmatrix}
= B^{-1}A^{-1}
$$

Both calculations produce the identical matrix.

#### The Meaning of the Reversed Order (The Socks and Shoes Principle)

The reversal of order can be understood through two perspectives:

- **The Transformation Perspective (Geometric Undoing):**
  When the product $AB$ acts on a column vector $x$:

$$
(AB)x = A(Bx)
$$

  Transformation $B$ is applied **first**, and transformation $A$ is applied **second**.
  To completely undo the composite effect and return to the original vector $x$, the operations must be reversed in reverse chronological order:
  - First, undo transformation $A$ by applying $A^{-1}$.
  - Second, undo transformation $B$ by applying $B^{-1}$.

  Applying the inverse operators to the output vector $y = A(Bx)$:

$$
B^{-1}(A^{-1} y) = B^{-1}(A^{-1}(A(Bx))) = B^{-1}(Bx) = x
$$

  This is known as the **shoes and socks principle**: you put on your socks first and your shoes second; to undo the process, you must remove your shoes first and your socks second.

- **Algebraic Cancellation:**
  If we mistakenly used the unreversed order $A^{-1}B^{-1}$:

$$
(AB)(A^{-1}B^{-1}) = A B A^{-1} B^{-1}
$$

  Because matrix multiplication is non-commutative ($BA^{-1} \neq A^{-1}B$ in general), $B$ and $A^{-1}$ cannot bypass each other to cancel into the identity. Only the reversed order places $B$ adjacent to $B^{-1}$, enabling immediate cancellation.

---

## Verification and Consistency Checks

### Check 1: Incorrect Order Calculation ($A^{-1}B^{-1}$)

Computing the unreversed product:

$$
A^{-1}B^{-1} =
\begin{pmatrix}
1 & -1 \\
0 & 1
\end{pmatrix}
\begin{pmatrix}
\frac{1}{2} & 0 \\
0 & \frac{1}{3}
\end{pmatrix}
= \begin{pmatrix}
\frac{1}{2} & -\frac{1}{3} \\
0 & \frac{1}{3}
\end{pmatrix}
$$

Comparing $(AB)^{-1}$ and $A^{-1}B^{-1}$:

$$
\begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} \\
0 & \frac{1}{3}
\end{pmatrix}
\neq
\begin{pmatrix}
\frac{1}{2} & -\frac{1}{3} \\
0 & \frac{1}{3}
\end{pmatrix}
$$

The entry at $(1, 2)$ differs ($-\frac{1}{2} \neq -\frac{1}{3}$). This demonstrates concretely that order matters and that $(AB)^{-1} \neq A^{-1}B^{-1}$.

### Check 2: Determinant Multiplicative Consistency

Using the determinant product rule:
- $\det A = 1$
- $\det B = (2)(3) = 6$
- $\det(AB) = \det A \cdot \det B = 1 \cdot 6 = 6$

Checking the inverse determinants:

$$
\det((AB)^{-1}) = \left(\frac{1}{2}\right)\left(\frac{1}{3}\right) - (0)\left(-\frac{1}{2}\right) = \frac{1}{6} = \frac{1}{\det(AB)}
$$

$$
\det(B^{-1}A^{-1}) = \det(B^{-1})\det(A^{-1}) = \left(\frac{1}{6}\right)(1) = \frac{1}{6}
$$

The determinants match $\frac{1}{6}$.

---

## Why This Exercise Matters

- **Core Rule for Matrix Algebra:** The reversed order property $(AB)^{-1} = B^{-1}A^{-1}$ extends to products of any number of matrices: $(A_1 A_2 \cdots A_k)^{-1} = A_k^{-1} \cdots A_2^{-1} A_1^{-1}$.
- **Transposition Analogy:** Reversal also applies to matrix transposition: $(AB)^T = B^T A^T$. Together, transposition and inversion are the two primary anti-homomorphisms in matrix algebra.
- **Solving Structural Equations:** In advanced linear algebra and numerical analysis, factors must be peeled off outer layers first when solving equations like $X = A^{-1} B C^{-1}$.
