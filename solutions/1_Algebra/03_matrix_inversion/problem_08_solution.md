# Problem 8: Inverse of a Transformation

## Question

The matrix

$$
S=
\begin{pmatrix}
2 & 0 \\
0 & \frac{1}{2}
\end{pmatrix}
$$

describes a scaling of the plane. Find $S^{-1}$ and explain geometrically what the inverse transformation does. Check the action of the pair $S,S^{-1}$ on one simple vector.

---

## Solution

### 1. Finding the Inverse Matrix $S^{-1}$

Matrix $S$ is a $2 \times 2$ diagonal matrix:

$$
S =
\begin{pmatrix}
2 & 0 \\
0 & \frac{1}{2}
\end{pmatrix}
$$

#### Method 1: Inversion of a Diagonal Matrix

For a diagonal matrix with non-zero entries on the main diagonal, the inverse is obtained by replacing each diagonal entry with its reciprocal:

$$
S^{-1} =
\begin{pmatrix}
\frac{1}{2} & 0 \\
0 & \frac{1}{\frac{1}{2}}
\end{pmatrix}
= \begin{pmatrix}
\frac{1}{2} & 0 \\
0 & 2
\end{pmatrix}
$$

#### Method 2: The 2x2 Inversion Formula

Using the standard determinant formula:

$$
\det S = (2)\left(\frac{1}{2}\right) - (0)(0) = 1 - 0 = 1
$$

Applying the $2 \times 2$ formula:

$$
S^{-1} = \frac{1}{1}
\begin{pmatrix}
\frac{1}{2} & 0 \\
0 & 2
\end{pmatrix}
= \begin{pmatrix}
\frac{1}{2} & 0 \\
0 & 2
\end{pmatrix}
$$

Both methods yield the same inverse matrix.

---

### 2. Geometric Interpretation of the Transformations

#### Action of the Forward Transformation $S$

Let vector $v$ be an arbitrary point in the Cartesian plane $\mathbb{R}^2$:

$$
v =
\begin{pmatrix}
x \\
y
\end{pmatrix}
$$

Applying $S$:

$$
Sv =
\begin{pmatrix}
2 & 0 \\
0 & \frac{1}{2}
\end{pmatrix}
\begin{pmatrix}
x \\
y
\end{pmatrix}
= \begin{pmatrix}
2x \\
\frac{1}{2}y
\end{pmatrix}
$$

The transformation $S$ acts on the plane by:
- **Stretching horizontally** along the $x$-axis by a scale factor of $2$.
- **Compressing vertically** along the $y$-axis by a scale factor of $\frac{1}{2}$ (halving the vertical coordinate).

Because $\det S = (2)\left(\frac{1}{2}\right) = 1$, the transformation preserves the total area of any geometric region (e.g., a unit square transforms into a $2 \times \frac{1}{2}$ rectangle of area $1$). Such volume-preserving transformations are called **equiareal** (or hyperbolic rotations / squeeze mappings).

#### Action of the Inverse Transformation $S^{-1}$

Applying $S^{-1}$ to an arbitrary vector $w$:

$$
w =
\begin{pmatrix}
x' \\
y'
\end{pmatrix}
$$

$$
S^{-1}w =
\begin{pmatrix}
\frac{1}{2} & 0 \\
0 & 2
\end{pmatrix}
\begin{pmatrix}
x' \\
y'
\end{pmatrix}
= \begin{pmatrix}
\frac{1}{2}x' \\
2y'
\end{pmatrix}
$$

The inverse transformation $S^{-1}$ geometrically **undoes** the scaling performed by $S$:
- It **compresses horizontally** along the $x$-axis by a factor of $\frac{1}{2}$, undoing the factor of $2$ stretch.
- It **stretches vertically** along the $y$-axis by a factor of $2$, undoing the factor of $\frac{1}{2}$ compression.

---

### 3. Checking the Action of the Pair $S, S^{-1}$ on a Simple Vector

Choose the simple test vector:

$$
v =
\begin{pmatrix}
3 \\
4
\end{pmatrix}
$$

#### Step 1: Apply Transformation $S$ to $v$

$$
v' = Sv =
\begin{pmatrix}
2 & 0 \\
0 & \frac{1}{2}
\end{pmatrix}
\begin{pmatrix}
3 \\
4
\end{pmatrix}
$$

Evaluating entries:

$$
v' =
\begin{pmatrix}
(2)(3) + (0)(4) \\
(0)(3) + \left(\frac{1}{2}\right)(4)
\end{pmatrix}
= \begin{pmatrix}
6 \\
2
\end{pmatrix}
$$

Under transformation $S$, the point $(3, 4)$ is mapped to $(6, 2)$.

#### Step 2: Apply Inverse Transformation $S^{-1}$ to $v'$

Now apply $S^{-1}$ to the transformed vector $v'$:

$$
S^{-1}v' = S^{-1}(Sv) =
\begin{pmatrix}
\frac{1}{2} & 0 \\
0 & 2
\end{pmatrix}
\begin{pmatrix}
6 \\
2
\end{pmatrix}
$$

Evaluating entries:

$$
S^{-1}v' =
\begin{pmatrix}
\left(\frac{1}{2}\right)(6) + (0)(2) \\
(0)(6) + (2)(2)
\end{pmatrix}
= \begin{pmatrix}
3 \\
4
\end{pmatrix}
= v
$$

The composite action $S^{-1}(Sv)$ returns the vector to its initial state $(3, 4)$.

#### Step 3: Check the Reverse Composite $S(S^{-1}v)$

Applying $S^{-1}$ first to $v$:

$$
v'' = S^{-1}v =
\begin{pmatrix}
\frac{1}{2} & 0 \\
0 & 2
\end{pmatrix}
\begin{pmatrix}
3 \\
4
\end{pmatrix}
= \begin{pmatrix}
\frac{3}{2} \\
8
\end{pmatrix}
$$

Now applying $S$ to $v''$:

$$
S(S^{-1}v) =
\begin{pmatrix}
2 & 0 \\
0 & \frac{1}{2}
\end{pmatrix}
\begin{pmatrix}
\frac{3}{2} \\
8
\end{pmatrix}
$$

Evaluating entries:

$$
S(S^{-1}v) =
\begin{pmatrix}
(2)\left(\frac{3}{2}\right) \\
\left(\frac{1}{2}\right)(8)
\end{pmatrix}
= \begin{pmatrix}
3 \\
4
\end{pmatrix}
= v
$$

In both orders of composition, the inverse transformation returns the vector to its starting position.

---

## Verification and Consistency Checks

### Check 1: Matrix Multiplication ($S S^{-1}$ and $S^{-1} S$)

Computing the direct algebraic matrix product:

$$
S S^{-1} =
\begin{pmatrix}
2 & 0 \\
0 & \frac{1}{2}
\end{pmatrix}
\begin{pmatrix}
\frac{1}{2} & 0 \\
0 & 2
\end{pmatrix}
$$

Evaluating entries:

$$
S S^{-1} =
\begin{pmatrix}
(2)\left(\frac{1}{2}\right) + (0)(0) & (2)(0) + (0)(2) \\
(0)\left(\frac{1}{2}\right) + \left(\frac{1}{2}\right)(0) & (0)(0) + \left(\frac{1}{2}\right)(2)
\end{pmatrix}
= \begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}
= I_2
$$

Similarly, $S^{-1} S = I_2$.

### Check 2: Invariant Curve Check (Hyperbolas)

For any point $(x, y)$, the product of coordinates after applying $S$ is:

$$
x' y' = (2x)\left(\frac{1}{2}y\right) = xy
$$

The family of hyperbolas $xy = c$ is mapped onto itself under both $S$ and $S^{-1}$. Points simply slide along the hyperbolic trajectories.

---

## Why This Exercise Matters

- **Geometric Essence of the Inverse:** Connects abstract matrix operations to their geometric role: an inverse matrix undoes the geometric distortions (stretches, rotations, shears) produced by the forward mapping.
- **Squeeze Mappings in Physics:** The matrix $S$ is a classic squeeze mapping, which represents volume-preserving phase space transformations in Hamiltonian mechanics (Liouville's theorem) and Lorentz boosts in special relativity.
- **Simplicity of Diagonal Systems:** Demonstrates that coordinate axes aligned with eigenvectors decouple into independent 1D scalar operations, where matrix inversion reduces to taking scalar reciprocals.
