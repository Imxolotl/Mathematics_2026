# Problem 8: Determinant of a Product

## Question

Let $A,B$ be square matrices such that $\det A=3$ and $\det B=-5$. Compute $\det(AB)$, $\det(BA)$ and, if it exists, $\det(A^{-1}B)$. Explain why the first two results are equal even though usually $AB\neq BA$.

---

## Solution

### 1. Multiplicative Property of the Determinant

For any two square matrices $M$ and $N$ of the same size $n \times n$, the determinant of their product is the product of their determinants:

$$
\det(MN) = \det M \cdot \det N
$$

---

### 2. Computation of $\det(AB)$ and $\det(BA)$

Applying the multiplicative property:

1. **Computation of $\det(AB)$:**

$$
\begin{aligned}
\det(AB) &= \det A \cdot \det B \\
         &= 3 \cdot (-5) \\
         &= -15
\end{aligned}
$$

2. **Computation of $\det(BA)$:**

$$
\begin{aligned}
\det(BA) &= \det B \cdot \det A \\
         &= (-5) \cdot 3 \\
         &= -15
\end{aligned}
$$

---

### 3. Existence and Computation of $\det(A^{-1}B)$

#### Condition for Existence

An inverse matrix $A^{-1}$ exists if and only if $\det A \neq 0$. Since $\det A = 3 \neq 0$, matrix $A$ is invertible, and $A^{-1}$ exists. Consequently, the product $A^{-1}B$ is well-defined.

#### Determinant of an Inverse Matrix

Since $A A^{-1} = I$, applying the product rule gives:

$$
\det(A A^{-1}) = \det A \cdot \det(A^{-1}) = \det I = 1
$$

Dividing by $\det A$:

$$
\det(A^{-1}) = \frac{1}{\det A}
$$

#### Computation of $\det(A^{-1}B)$

Using the product rule:

$$
\begin{aligned}
\det(A^{-1}B) &= \det(A^{-1}) \cdot \det B \\
             &= \frac{1}{\det A} \cdot \det B \\
             &= \frac{1}{3} \cdot (-5) \\
             &= -\frac{5}{3}
\end{aligned}
$$

---

### 4. Explanation: Why $\det(AB) = \det(BA)$ While $AB \neq BA$

The equality $\det(AB) = \det(BA)$ holds even when the matrix products $AB$ and $BA$ are unequal due to the difference between matrix multiplication and scalar multiplication:

1. **Non-Commutativity of Matrices:**
   In the ring of $n \times n$ matrices $M_{n \times n}(\mathbb{R})$ with $n \ge 2$, matrix multiplication is generally **non-commutative**:

$$
AB \neq BA
$$

   The entry at row $i$, column $j$ in $AB$ involves row $i$ of $A$ and column $j$ of $B$, whereas in $BA$ it involves row $i$ of $B$ and column $j$ of $A$. These combinations are usually distinct.

2. **Commutativity of the Scalar Field:**
   The determinant is a scalar-valued function $\det \colon M_{n \times n}(\mathbb{R}) \to \mathbb{R}$. It maps matrices into the real numbers $\mathbb{R}$. For any two real numbers $\alpha, \beta \in \mathbb{R}$, scalar multiplication is commutative:

$$
\alpha \cdot \beta = \beta \cdot \alpha
$$

   Therefore:

$$
\det(AB) = (\det A)(\det B) = (\det B)(\det A) = \det(BA)
$$

3. **Geometric Interpretation (Volume Scaling):**
   A linear transformation $T_M(x) = Mx$ scales the $n$-dimensional volume of any region by the factor $|\det M|$, and either preserves or reverses orientation according to the sign of $\det M$.
   - The transformation $T_{AB} = T_A \circ T_B$ first applies transformation $B$ (scaling volume by $|-5| = 5$ and reversing orientation) and then applies transformation $A$ (scaling volume by $|3| = 3$). The combined scaling factor is $5 \cdot 3 = 15$ with reversed orientation, giving determinant $-15$.
   - The transformation $T_{BA} = T_B \circ T_A$ applies the two mappings in reverse order. The composite volume scaling factor is $3 \cdot 5 = 15$ with reversed orientation, giving determinant $-15$.
   - Although the composite geometric operations distort space differently (yielding distinct final shapes and orientations, so $AB \neq BA$), the net volume scale factor and overall orientation change are identical.

---

## Verification and Consistency Checks

1. **Concrete Non-Commuting $2 \times 2$ Example:**
   Choose matrices $A$ and $B$ with $\det A = 3$ and $\det B = -5$:

$$
A =
\begin{pmatrix}
1 & 1 \\
0 & 3
\end{pmatrix}, \qquad
B =
\begin{pmatrix}
1 & 0 \\
2 & -5
\end{pmatrix}
$$

   Checking their determinants:
   - $\det A = (1)(3) - (1)(0) = 3$
   - $\det B = (1)(-5) - (0)(2) = -5$

   **Product $AB$:**

$$
AB =
\begin{pmatrix}
1 & 1 \\
0 & 3
\end{pmatrix}
\begin{pmatrix}
1 & 0 \\
2 & -5
\end{pmatrix}
$$

   Multiplying rows by columns:

$$
AB =
\begin{pmatrix}
1(1) + 1(2) & 1(0) + 1(-5) \\
0(1) + 3(2) & 0(0) + 3(-5)
\end{pmatrix}
= \begin{pmatrix}
3 & -5 \\
6 & -15
\end{pmatrix}
$$

$$
\det(AB) = (3)(-15) - (-5)(6) = -45 - (-30) = -15
$$

   **Product $BA$:**

$$
BA =
\begin{pmatrix}
1 & 0 \\
2 & -5
\end{pmatrix}
\begin{pmatrix}
1 & 1 \\
0 & 3
\end{pmatrix}
$$

   Multiplying rows by columns:

$$
BA =
\begin{pmatrix}
1(1) + 0(0) & 1(1) + 0(3) \\
2(1) - 5(0) & 2(1) - 5(3)
\end{pmatrix}
= \begin{pmatrix}
1 & 1 \\
2 & -13
\end{pmatrix}
$$

$$
\det(BA) = (1)(-13) - (1)(2) = -13 - 2 = -15
$$

   Comparing the two:

$$
AB =
\begin{pmatrix}
3 & -5 \\
6 & -15
\end{pmatrix}
\neq
\begin{pmatrix}
1 & 1 \\
2 & -13
\end{pmatrix}
= BA
$$

   Yet $\det(AB) = \det(BA) = -15$, confirming both non-commutativity and determinant equality.

   **Product $A^{-1}B$:**
   The inverse of $A$ is:

$$
A^{-1} = \frac{1}{3}
\begin{pmatrix}
3 & -1 \\
0 & 1
\end{pmatrix}
= \begin{pmatrix}
1 & -\frac{1}{3} \\
0 & \frac{1}{3}
\end{pmatrix}
$$

$$
A^{-1}B =
\begin{pmatrix}
1 & -\frac{1}{3} \\
0 & \frac{1}{3}
\end{pmatrix}
\begin{pmatrix}
1 & 0 \\
2 & -5
\end{pmatrix}
$$

   Multiplying rows by columns:

$$
A^{-1}B =
\begin{pmatrix}
1 - \frac{2}{3} & 0 + \frac{5}{3} \\
0 + \frac{2}{3} & 0 - \frac{5}{3}
\end{pmatrix}
= \begin{pmatrix}
\frac{1}{3} & \frac{5}{3} \\
\frac{2}{3} & -\frac{5}{3}
\end{pmatrix}
$$

$$
\det(A^{-1}B) = \left(\frac{1}{3}\right)\left(-\frac{5}{3}\right) - \left(\frac{5}{3}\right)\left(\frac{2}{3}\right) = -\frac{5}{9} - \frac{10}{9} = -\frac{15}{9} = -\frac{5}{3}
$$

   This matches $\det(A^{-1}B) = -\frac{5}{3}$.

2. **Inverse of the Product Check:**
   Using the inverse product rule $(AB)^{-1} = B^{-1} A^{-1}$:

$$
\det((AB)^{-1}) = \frac{1}{\det(AB)} = -\frac{1}{15}
$$

   On the other hand:

$$
\det(B^{-1} A^{-1}) = \det(B^{-1}) \det(A^{-1}) = \left(-\frac{1}{5}\right)\left(\frac{1}{3}\right) = -\frac{1}{15}
$$

   Both results are consistent.

---

## Why This Exercise Matters

- **Group Homomorphism:** The multiplicative property establishes that the determinant is a group homomorphism from the general linear group $\mathrm{GL}_n(\mathbb{R})$ to the multiplicative group of non-zero real numbers $(\mathbb{R}^\times, \cdot)$.
- **Similarity Invariance:** Because $\det(AB) = \det(BA)$, for any invertible change-of-basis matrix $P$, the determinant of a conjugate matrix satisfies $\det(P^{-1} M P) = \det(P^{-1})\det(M)\det(P) = \det(M)$. This proves that the determinant is an intrinsic property of a linear operator, completely independent of the choice of coordinate basis.
- **Algebraic Distinction:** Reinforces the crucial conceptual boundary between matrix algebra (which is non-commutative) and scalar invariants (which commute).
