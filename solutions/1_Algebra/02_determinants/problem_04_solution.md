# Problem 4: Triangular Matrix

## Question

Without expanding the determinant, compute

$$
\det
\begin{pmatrix}
2 & 4 & 1 \\
0 & -3 & 5 \\
0 & 0 & 7 \\
\end{pmatrix}.
$$

State the rule for an arbitrary triangular matrix and explain it using this example.

---

## Solution

### 1. Classification of the Matrix

Let

$$
T =
\begin{pmatrix}
2 & 4 & 1 \\
0 & -3 & 5 \\
0 & 0 & 7 \\
\end{pmatrix}
$$

A square matrix is called **upper triangular** if all entries strictly below the main diagonal are zero:

$$
t_{ij} = 0 \quad (i > j)
$$

In matrix $T$, the entries below the diagonal are $t_{21} = 0$, $t_{31} = 0$, and $t_{32} = 0$. Hence, $T$ is an upper triangular matrix.

---

### 2. General Rule for Triangular Matrices

**Theorem:**
The determinant of any $n \times n$ triangular matrix (whether upper triangular, lower triangular, or diagonal) equals the product of its main diagonal entries:

$$
\det T = \prod_{i=1}^n t_{ii} = t_{11} \cdot t_{22} \cdots t_{nn}
$$

---

### 3. Computation

Applying the rule directly to matrix $T$:
- $t_{11} = 2$
- $t_{22} = -3$
- $t_{33} = 7$

Multiplying the diagonal entries:

$$
\begin{aligned}
\det T &= t_{11} \cdot t_{22} \cdot t_{33} \\
       &= 2 \cdot (-3) \cdot 7 \\
       &= -6 \cdot 7 \\
       &= -42
\end{aligned}
$$

---

### 4. Explanation Using the Example

The triangular matrix rule can be explained in two ways:

#### Explanation 1: Successive Laplace Expansion along the First Column

Consider expanding $\det T$ along the **first column**:

$$
\det T = t_{11} C_{11} + t_{21} C_{21} + t_{31} C_{31}
$$

Because all entries below the first diagonal entry are zero ($t_{21} = 0$ and $t_{31} = 0$), the second and third terms vanish entirely:

$$
\det T = 2 \cdot C_{11} + 0 + 0 = 2 \cdot (-1)^{1+1} \det
\begin{pmatrix}
-3 & 5 \\
0 & 7 \\
\end{pmatrix}
$$

Now compute the $2 \times 2$ determinant. Notice that this submatrix is again upper triangular:

$$
\det
\begin{pmatrix}
-3 & 5 \\
0 & 7 \\
\end{pmatrix}
= (-3)(7) - (5)(0) = (-3)(7) = -21
$$

Substituting this result back into the main expression:

$$
\det T = 2 \cdot [(-3) \cdot (7)] = -42
$$

At each stage, the only surviving non-zero contribution is the diagonal entry multiplied by the remaining lower-right diagonal submatrix.

#### Explanation 2: Leibniz Formula (Permutations)

By definition, the determinant of an $n \times n$ matrix is:

$$
\det T = \sum_{\sigma \in S_n} \mathrm{sgn}(\sigma) \prod_{i=1}^n t_{i,\sigma(i)}
$$

where the sum runs over all permutations $\sigma$ of $\{1, 2, \dots, n\}$.
- For any permutation $\sigma$ other than the identity permutation ($\sigma \neq \mathrm{id}$), there exists at least one index $i$ such that $\sigma(i) < i$.
- For an upper triangular matrix, any entry with row index greater than column index ($i > j$) is zero ($t_{i, \sigma(i)} = 0$).
- Consequently, every product corresponding to a non-identity permutation contains at least one zero factor and evaluates to $0$.

The only surviving term is the identity permutation $\sigma = (1, 2, 3)$, which gives:

$$
\det T = \mathrm{sgn}(\mathrm{id}) \cdot t_{11} t_{22} t_{33} = 2 \cdot (-3) \cdot 7 = -42
$$

---

## Verification and Consistency Checks

1. **Verification via Sarrus' Rule:**

$$
\begin{aligned}
\det T &= [2 \cdot (-3) \cdot 7 + 4 \cdot 5 \cdot 0 + 1 \cdot 0 \cdot 0] - [0 \cdot (-3) \cdot 1 + 0 \cdot 5 \cdot 2 + 7 \cdot 0 \cdot 4] \\
       &= [-42 + 0 + 0] - [0 + 0 + 0] \\
       &= -42
\end{aligned}
$$

2. **Invertibility Status:**
   A triangular matrix is invertible if and only if **all** of its diagonal entries are non-zero:

$$
\det T \neq 0 \iff \prod_{i=1}^n t_{ii} \neq 0
$$

   This condition requires $t_{ii} \neq 0$ for each $i \in \{1, 2, \dots, n\}$. Here, the diagonal entries are $2, -3, 7$. Since none of them is zero, $\det T = -42 \neq 0$, and the matrix is invertible.

---

## Why This Exercise Matters

- **Computational Efficiency:** Computing an $n \times n$ determinant directly using cofactors or definitions requires $\mathcal{O}(n!)$ operations. Reducing a matrix to triangular form takes $\mathcal{O}(n^3)$ operations, after which the determinant is found instantly by multiplying $n$ numbers.
- **Connection to Gaussian Elimination:** Gaussian elimination transforms an arbitrary square matrix into an upper triangular matrix. Tracking row operations allows determinants of large matrices to be computed efficiently in scientific computing.
- **Eigenvalues of Triangular Matrices:** The diagonal entries of a triangular matrix are also its eigenvalues, because $\det(T - \lambda I) = \prod_{i=1}^n (t_{ii} - \lambda) = 0$.
