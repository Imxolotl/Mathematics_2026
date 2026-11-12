# Problem 3: Inconsistent System

## Question

Solve or show that the system is inconsistent:

$$
\begin{cases}
x+2y=3, \\
2x+4y=7.
\end{cases}
$$

Show how the contradiction appears in the matrix after elimination and interpret it in terms of equations.

---

## Solution

### 1. Set Up the Augmented Matrix

We write the system as an augmented matrix $[A \mid b]$:

$$
\begin{pmatrix}
1 & 2 & \mid & 3 \\
2 & 4 & \mid & 7
\end{pmatrix}
$$

---

### 2. Elimination

We use the pivot in row 1 ($a_{11} = 1$) to eliminate the $x$-term in row 2:

Apply the elementary row operation $R_2 \leftarrow R_2 - 2R_1$:

$$
R_2 - 2R_1 = (2 - 2(1), \; 4 - 2(2) \mid 7 - 2(3)) = (0, \; 0 \mid 1)
$$

The augmented matrix becomes:

$$
\begin{pmatrix}
1 & 2 & \mid & 3 \\
0 & 0 & \mid & 1
\end{pmatrix}
$$

---

### 3. Appearance of the Contradiction

The second row of the echelon matrix reads:

$$
\begin{pmatrix}
0 & 0 & \mid & 1
\end{pmatrix}
$$

Translating this row back into equation form gives:

$$
0x + 0y = 1
$$

Since $0x + 0y = 0$ for all real numbers $x$ and $y$, the statement reduces to:

$$
0 = 1
$$

This is a mathematical contradiction ($0 \neq 1$). Because no choice of variables $(x, y)$ can make this equality true, the system has **no solution**. A system with no solution is termed **inconsistent**.

The solution set is the empty set:

$$
S = \emptyset
$$

---

## Geometric and Algebraic Interpretation

### Geometric Interpretation (Parallel Lines)

Each linear equation in two variables represents a straight line in the Cartesian plane $\mathbb{R}^2$:

1. First line $L_1$:

$$
x + 2y = 3 \implies 2y = -x + 3 \implies y = -\frac{1}{2}x + \frac{3}{2}
$$

2. Second line $L_2$:

$$
2x + 4y = 7 \implies 4y = -2x + 7 \implies y = -\frac{1}{2}x + \frac{7}{4}
$$

- Both lines have the exact same slope $m = -\frac{1}{2}$.
- The lines have different $y$-intercepts: $\frac{3}{2} \neq \frac{7}{4}$.

Therefore, $L_1$ and $L_2$ are distinct, parallel lines. In Euclidean geometry, parallel lines never intersect. Because a solution to a linear system corresponds to an intersection point, the lack of an intersection point directly reflects the fact that the system is inconsistent.

### Algebraic Interpretation (Linear Combination of Left-Hand Sides)

Notice what happens if we multiply the entire first equation by $2$:

$$
2(x + 2y) = 2(3) \implies 2x + 4y = 6
$$

Comparing this with the second equation:

$$
2x + 4y = 7
$$

The left-hand sides are identical expressions ($2x + 4y$), yet the system demands that this same expression simultaneously equals $6$ and $7$. Since a single quantity cannot equal two distinct numbers at the same time, no solution exists.

---

## Verification and Consistency Checks

### Check 1: Determinant of the Coefficient Matrix

The coefficient matrix is:

$$
A =
\begin{pmatrix}
1 & 2 \\
2 & 4
\end{pmatrix}
$$

Compute its determinant:

$$
\det A = (1)(4) - (2)(2) = 4 - 4 = 0
$$

A zero determinant means that $A$ is singular (not invertible). For a square matrix $A$, $\det A = 0$ indicates that the system $Ax = b$ either has no solution or infinitely many solutions, but never exactly one solution.

### Check 2: Rank Comparison (Rouché–Capelli Theorem)

- The coefficient matrix after elimination has one nonzero row, so $\mathrm{rank}(A) = 1$.
- The augmented matrix $[A \mid b]$ after elimination has two nonzero rows, so $\mathrm{rank}([A \mid b]) = 2$.
- Since $\mathrm{rank}(A) \neq \mathrm{rank}([A \mid b])$, the Rouché–Capelli theorem confirms that the system is inconsistent.

---

## Why This Exercise Matters

1. **Definite Detection:** Inconsistency is not detected by guessing; it appears systematically during Gaussian elimination as a row of zeros on the left with a nonzero entry on the right: $(0 \; 0 \; \dots \; 0 \mid c)$ with $c \neq 0$.
2. **Geometric Intuition:** Recognizing that linear equations represent geometric objects (such as lines or planes) connects abstract algebraic contradictions ($0 = 1$) to geometric properties (parallel non-intersecting lines).
3. **Difference Between No Solution and Zero Solution:** Having "no solution" means the solution set is empty ($\emptyset$). This is entirely different from having the number zero as a solution (e.g., $(0, 0)$).

