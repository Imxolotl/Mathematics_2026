# Problem 7: Using Properties Instead of Recomputing

## Question

Suppose that for a $3\times3$ matrix, $\det A=-4$. Compute

$$
\det(2A),\qquad \det(A^T),\qquad \det(A^2),\qquad \det(-A).
$$

Justify each answer using the appropriate property.

---

## Solution

### 1. Computation of $\det(2A)$

**Property (Scaling by a Scalar):**
For any $n \times n$ matrix $M$ and any scalar $c \in \mathbb{R}$, multiplying the matrix by $c$ scales each of its $n$ rows by $c$. By the multilinearity of the determinant with respect to rows:

$$
\det(cM) = c^n \det M
$$

**Computation:**
Here, matrix $A$ has dimension $n = 3$, scalar $c = 2$, and $\det A = -4$:

$$
\begin{aligned}
\det(2A) &= 2^3 \det A \\
         &= 8 \cdot (-4) \\
         &= -32
\end{aligned}
$$

A common mistake is writing $\det(2A) = 2\det A = -8$; the factor of $2$ must be raised to the power of the matrix dimension $n = 3$.

---

### 2. Computation of $\det(A^T)$

**Property (Transpose Invariance):**
For any square matrix $M$, the determinant of its transpose equals the determinant of the original matrix:

$$
\det(M^T) = \det M
$$

**Justification:**
Transposition interchanges rows and columns. In the Leibniz formula for the determinant:

$$
\det M = \sum_{\sigma \in S_n} \mathrm{sgn}(\sigma) \prod_{i=1}^n m_{i,\sigma(i)}
$$

inverting each permutation $\sigma$ leaves the sign unchanged ($\mathrm{sgn}(\sigma^{-1}) = \mathrm{sgn}(\sigma)$), and the products of entries remain identical.

**Computation:**

$$
\det(A^T) = \det A = -4
$$

---

### 3. Computation of $\det(A^2)$

**Property (Multiplicative Property of Determinants):**
For any two square matrices $M$ and $N$ of the same size, the determinant of their product is the product of their determinants:

$$
\det(MN) = \det M \cdot \det N
$$

Applying this rule to matrix powers, where $A^2 = A \cdot A$:

$$
\det(A^2) = \det(A \cdot A) = (\det A) \cdot (\det A) = (\det A)^2
$$

**Computation:**
Since $\det A = -4$:

$$
\begin{aligned}
\det(A^2) &= (-4)^2 \\
          &= 16
\end{aligned}
$$

In general, for any positive integer $k$, $\det(A^k) = (\det A)^k$.

---

### 4. Computation of $\det(-A)$

**Property (Negation of an $n \times n$ Matrix):**
Negating a matrix is equivalent to multiplying the matrix by the scalar $c = -1$:

$$
-A = (-1)A
$$

Applying the scalar multiplication property with $n = 3$ and $c = -1$:

$$
\det(-A) = \det((-1)A) = (-1)^n \det A
$$

Since the matrix dimension $n = 3$ is odd, $(-1)^3 = -1$:

$$
\begin{aligned}
\det(-A) &= (-1)^3 \det A \\
         &= -1 \cdot (-4) \\
         &= 4
\end{aligned}
$$

For an even-dimensional matrix ($n$ even), $(-1)^n = 1$, so $\det(-M) = \det M$. For an odd-dimensional matrix ($n$ odd), $\det(-M) = -\det M$.

---

### 5. Summary of Results

$$
\det(2A) = -32, \qquad \det(A^T) = -4, \qquad \det(A^2) = 16, \qquad \det(-A) = 4
$$

---

## Verification and Consistency Checks

1. **Concrete Diagonal Matrix Check:**
   Consider a diagonal $3 \times 3$ matrix $D$ with determinant $-4$:

$$
D =
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & -4 \\
\end{pmatrix}
$$

   Computing the four quantities directly on $D$:

   - **Scalar Multiple $2D$:**

$$
2D =
\begin{pmatrix}
2 & 0 & 0 \\
0 & 2 & 0 \\
0 & 0 & -8 \\
\end{pmatrix}
\implies \det(2D) = (2)(2)(-8) = -32
$$

   - **Transpose $D^T$:**
     Since $D$ is diagonal, $D^T = D$, so $\det(D^T) = \det D = -4$.

   - **Matrix Square $D^2$:**

$$
D^2 =
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 16 \\
\end{pmatrix}
\implies \det(D^2) = (1)(1)(16) = 16
$$

   - **Negation $-D$:**

$$
-D =
\begin{pmatrix}
-1 & 0 & 0 \\
0 & -1 & 0 \\
0 & 0 & 4 \\
\end{pmatrix}
\implies \det(-D) = (-1)(-1)(4) = 4
$$

   All four direct calculations match the theoretical results derived from the properties.

2. **Cross-Consistency Check Between Operations:**
   Observe that $2A = (-2)(-A)$. Using the scalar multiplication rule on $-A$:

$$
\det(2A) = \det((-2)(-A)) = (-2)^3 \det(-A) = -8 \cdot 4 = -32
$$

   This matches the value of $\det(2A) = -32$ computed in Step 1.

---

## Why This Exercise Matters

- **Avoiding Unnecessary Computation:** In applications with large matrices ($n = 100$ or $n = 1000$), recalculating determinants from scratch requires $\mathcal{O}(n^3)$ operations. Knowing determinant properties allows instant evaluation in $\mathcal{O}(1)$ time.
- **Dimensionality Scaling:** Emphasizes that determinants scale with the $n$-th power of a scalar factor, corresponding to how $n$-dimensional volume scales when all side lengths are multiplied by $c$ ($\mathrm{Volume} \propto c^n$).
- **Parity in Linear Transformations:** The formula $\det(-A) = (-1)^n \det A$ explains why reflecting all coordinate axes reverses orientation in odd-dimensional spaces ($\mathbb{R}^3$) but preserves orientation in even-dimensional spaces ($\mathbb{R}^2$, $\mathbb{R}^4$).
