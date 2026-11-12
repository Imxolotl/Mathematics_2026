# Problem 4: Gauss-Jordan

## Question

Find $A^{-1}$ using the Gauss–Jordan method for

$$
A=
\begin{pmatrix}
1 & 2 \\
3 & 5
\end{pmatrix}.
$$

Show the augmented matrix $[A\mid I]$ after successive operations and explain why obtaining $I$ on the left gives the inverse on the right.

---

## Solution

### 1. The Principle of Gauss-Jordan Inversion

To invert an $n \times n$ matrix $A$, we form the augmented matrix $[A \mid I_n]$ by adjoining the $n \times n$ identity matrix to the right of $A$.

Elementary row operations are applied systematically to transform the left block into the identity matrix $I_n$:

$$
[A \mid I_n] \xrightarrow{\mathrm{row\ operations}} [I_n \mid B]
$$

When the left block reaches $I_n$, the resulting right block $B$ is the matrix inverse $A^{-1}$.

#### Why Obtaining $I$ on the Left Gives $A^{-1}$ on the Right

Every elementary row operation corresponds to left-multiplication by an elementary matrix $E_k$. If a sequence of $k$ elementary row operations reduces $A$ to the identity matrix $I$:

$$
E_k \cdots E_2 E_1 A = I
$$

Letting $E = E_k \cdots E_2 E_1$ denote the product of all elementary matrices:

$$
E A = I \implies E = A^{-1}
$$

Because the identical row operations are simultaneously applied to the right block $I$:

$$
E I = E = A^{-1}
$$

Therefore, whatever sequence of operations transforms $A$ into $I$ inevitably transforms $I$ into $A^{-1}$.

---

### 2. Step-by-Step Gauss-Jordan Elimination

Starting with the augmented matrix $[A \mid I_2]$:

$$
\begin{pmatrix}
1 & 2 & \mid & 1 & 0 \\
3 & 5 & \mid & 0 & 1
\end{pmatrix}
$$

#### Step 1: Eliminate Entry $a_{21}$ in Row 2

Row operation: subtract $3$ times row 1 from row 2:

$$
R_2 \leftarrow R_2 - 3 R_1
$$

Computing the new row 2 entries:
- Left block: $(3 - 3(1), 5 - 3(2)) = (0, 5 - 6) = (0, -1)$
- Right block: $(0 - 3(1), 1 - 3(0)) = (-3, 1)$

The augmented matrix becomes:

$$
\begin{pmatrix}
1 & 2 & \mid & 1 & 0 \\
0 & -1 & \mid & -3 & 1
\end{pmatrix}
$$

#### Step 2: Scale Row 2 to Make the Second Pivot Equal to $1$

Row operation: multiply row 2 by $-1$:

$$
R_2 \leftarrow -R_2
$$

Computing the new row 2 entries:
- Left block: $-(0, -1) = (0, 1)$
- Right block: $-(-3, 1) = (3, -1)$

The augmented matrix becomes:

$$
\begin{pmatrix}
1 & 2 & \mid & 1 & 0 \\
0 & 1 & \mid & 3 & -1
\end{pmatrix}
$$

#### Step 3: Eliminate Entry $a_{12}$ in Row 1

Row operation: subtract $2$ times row 2 from row 1:

$$
R_1 \leftarrow R_1 - 2 R_2
$$

Computing the new row 1 entries:
- Left block: $(1 - 2(0), 2 - 2(1)) = (1, 0)$
- Right block: $(1 - 2(3), 0 - 2(-1)) = (1 - 6, 0 + 2) = (-5, 2)$

The augmented matrix reaches reduced row echelon form (RREF):

$$
\begin{pmatrix}
1 & 0 & \mid & -5 & 2 \\
0 & 1 & \mid & 3 & -1
\end{pmatrix}
$$

---

### 3. Reading Off the Inverse Matrix

The left block is now the identity matrix $I_2$. The right block is the computed inverse:

$$
A^{-1} =
\begin{pmatrix}
-5 & 2 \\
3 & -1
\end{pmatrix}
$$

---

## Verification and Consistency Checks

### Check 1: Verification by Multiplication ($A A^{-1}$)

Computing the product $A A^{-1}$:

$$
A A^{-1} =
\begin{pmatrix}
1 & 2 \\
3 & 5
\end{pmatrix}
\begin{pmatrix}
-5 & 2 \\
3 & -1
\end{pmatrix}
$$

Evaluating each entry:
- Row 1 · Column 1: $(1)(-5) + (2)(3) = -5 + 6 = 1$
- Row 1 · Column 2: $(1)(2) + (2)(-1) = 2 - 2 = 0$
- Row 2 · Column 1: $(3)(-5) + (5)(3) = -15 + 15 = 0$
- Row 2 · Column 2: $(3)(2) + (5)(-1) = 6 - 5 = 1$

$$
A A^{-1} =
\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}
= I_2
$$

### Check 2: Verification by Multiplication ($A^{-1} A$)

Computing the product in reverse order:

$$
A^{-1} A =
\begin{pmatrix}
-5 & 2 \\
3 & -1
\end{pmatrix}
\begin{pmatrix}
1 & 2 \\
3 & 5
\end{pmatrix}
$$

Evaluating each entry:
- Row 1 · Column 1: $(-5)(1) + (2)(3) = -5 + 6 = 1$
- Row 1 · Column 2: $(-5)(2) + (2)(5) = -10 + 10 = 0$
- Row 2 · Column 1: $(3)(1) + (-1)(3) = 3 - 3 = 0$
- Row 2 · Column 2: $(3)(2) + (-1)(5) = 6 - 5 = 1$

$$
A^{-1} A =
\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}
= I_2
$$

### Check 3: Using the 2x2 Inverse Formula

For matrix $A$:

$$
A =
\begin{pmatrix}
1 & 2 \\
3 & 5
\end{pmatrix}
$$

The determinant is $\det A = (1)(5) - (2)(3) = 5 - 6 = -1$.
Applying the formula:

$$
A^{-1} = \frac{1}{-1}
\begin{pmatrix}
5 & -2 \\
-3 & 1
\end{pmatrix}
= \begin{pmatrix}
-5 & 2 \\
3 & -1
\end{pmatrix}
$$

The result matches the output of Gauss–Jordan elimination.

---

## Why This Exercise Matters

- **Generalizability:** Unlike the $2 \times 2$ determinant formula, the Gauss–Jordan elimination algorithm generalizes directly to $n \times n$ matrices of any dimension ($3 \times 3$, $4 \times 4$, etc.).
- **Algorithmic Uniformity:** Gauss–Jordan solves the $n$ simultaneous vector equations $A x_i = e_i$ all at once, illustrating how linear systems and matrix inversion share the same computational engine.
- **Early Singularity Detection:** If at any stage a pivot position contains only zeros and cannot be rescued by row swapping, the algorithm terminates immediately, proving that the matrix is singular without computing full determinants.
