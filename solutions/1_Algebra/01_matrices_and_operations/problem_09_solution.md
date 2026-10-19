# Problem 9: Composing Transformations

## Question

Let

$$
S = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix}, \qquad
R = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}.
$$

The matrix $S$ describes nonuniform scaling, while $R$ describes a $90^\circ$ counterclockwise rotation.
For

$$
x = \begin{pmatrix} 1 \\ 2 \end{pmatrix}
$$

compute $RSx$ and $SRx$. Compare the results and explain geometrically why the order of these transformations matters.

---

## Geometric Meaning of the Matrices

Every $2 \times 2$ matrix defines a linear transformation of the coordinate plane $\mathbb{R}^2$. Let us see how $S$ and $R$ transform an arbitrary vector $(x, y)^T$:

### Nonuniform Scaling Matrix $S$

$$
S \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 2x \\ y \end{pmatrix}
$$

- The $x$-coordinate is multiplied by $2$.
- The $y$-coordinate is unchanged.
- Geometrically: a horizontal stretch by a factor of 2 along the $x$-axis.

### $90^\circ$ Counterclockwise Rotation Matrix $R$

Recall the general rotation matrix:

$$
R(\theta) = \begin{pmatrix} \cos\theta & -\sin\theta \\ \sin\theta & \cos\theta \end{pmatrix}
$$

For $\theta = 90^\circ$, we have $\cos 90^\circ = 0$ and $\sin 90^\circ = 1$:

$$
R = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}
$$

Applying $R$ to a vector:

$$
R \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} -y \\ x \end{pmatrix}
$$

- Geometrically: rotates every vector by $90^\circ$ counterclockwise around the origin.

---

## Step 1 — Compute $RSx$

The notation $RSx$ means: **apply $S$ first, then apply $R$ to the result** ($R(Sx)$).

### Step 1a: Compute $Sx$

We multiply $x$ by $S$:

$$
Sx = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix}
$$

Computing each entry:

- Row 1: $2 \cdot 1 + 0 \cdot 2 = 2$
- Row 2: $0 \cdot 1 + 1 \cdot 2 = 2$

$$
Sx = \begin{pmatrix} 2 \\ 2 \end{pmatrix}
$$

### Step 1b: Multiply the intermediate result by $R$

Now multiply the intermediate vector $Sx$ by $R$:

$$
RSx = R(Sx) = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 2 \\ 2 \end{pmatrix}
$$

Computing each entry:

- Row 1: $0 \cdot 2 + (-1) \cdot 2 = -2$
- Row 2: $1 \cdot 2 + 0 \cdot 2 = 2$

### Result for $RSx$

$$
RSx = \begin{pmatrix} -2 \\ 2 \end{pmatrix}
$$

---

### Alternative Method: Compute the Matrix Product $RS$ First

By associativity, $R(Sx) = (RS)x$.

$$
\begin{aligned}
RS &= \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \\
&= \begin{pmatrix} 0 \cdot 2 + (-1) \cdot 0 & 0 \cdot 0 + (-1) \cdot 1 \\ 1 \cdot 2 + 0 \cdot 0 & 1 \cdot 0 + 0 \cdot 1 \end{pmatrix} \\
&= \begin{pmatrix} 0 & -1 \\ 2 & 0 \end{pmatrix}
\end{aligned}
$$

Multiplying by vector $x$:

$$
(RS)x = \begin{pmatrix} 0 & -1 \\ 2 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} -2 \\ 2 \end{pmatrix}
$$

Both calculation paths yield the same vector. ✅

---

## Step 2 — Compute $SRx$

The notation $SRx$ means: **apply $R$ first, then apply $S$ to the result** ($S(Rx)$).

### Step 2a: Compute $Rx$

We multiply $x$ by $R$:

$$
Rx = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix}
$$

Computing each entry:

- Row 1: $0 \cdot 1 + (-1) \cdot 2 = -2$
- Row 2: $1 \cdot 1 + 0 \cdot 2 = 1$

$$
Rx = \begin{pmatrix} -2 \\ 1 \end{pmatrix}
$$

### Step 2b: Multiply the intermediate result by $S$

Now multiply the intermediate vector $Rx$ by $S$:

$$
SRx = S(Rx) = \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} -2 \\ 1 \end{pmatrix}
$$

Computing each entry:

- Row 1: $2 \cdot (-2) + 0 \cdot 1 = -4$
- Row 2: $0 \cdot (-2) + 1 \cdot 1 = 1$

### Result for $SRx$

$$
SRx = \begin{pmatrix} -4 \\ 1 \end{pmatrix}
$$

---

### Alternative Method: Compute the Matrix Product $SR$ First

$$
\begin{aligned}
SR &= \begin{pmatrix} 2 & 0 \\ 0 & 1 \end{pmatrix} \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \\
&= \begin{pmatrix} 2 \cdot 0 + 0 \cdot 1 & 2 \cdot (-1) + 0 \cdot 0 \\ 0 \cdot 0 + 1 \cdot 1 & 0 \cdot (-1) + 1 \cdot 0 \end{pmatrix} \\
&= \begin{pmatrix} 0 & -2 \\ 1 & 0 \end{pmatrix}
\end{aligned}
$$

Multiplying by vector $x$:

$$
(SR)x = \begin{pmatrix} 0 & -2 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \end{pmatrix} = \begin{pmatrix} -4 \\ 1 \end{pmatrix}
$$

Both calculation paths yield the same vector. ✅

---

## Step 3 — Comparison of the Results

Comparing the resulting vectors:

$$
RSx = \begin{pmatrix} -2 \\ 2 \end{pmatrix}, \qquad
SRx = \begin{pmatrix} -4 \\ 1 \end{pmatrix}
$$

Clearly:

$$
RSx \neq SRx
$$

Comparing the composite transformation matrices:

$$
RS = \begin{pmatrix} 0 & -1 \\ 2 & 0 \end{pmatrix}, \qquad
SR = \begin{pmatrix} 0 & -2 \\ 1 & 0 \end{pmatrix}
$$

Clearly:

$$
RS \neq SR
$$

Matrix multiplication does not commute.

---

## Step 4 — Geometric Explanation: Why Does the Order Matter?

Matrix multiplication represents the **composition of functions**: $RS$ means do $S$ first, then $R$.

Let us trace the two paths geometrically:

### Path 1: $RSx$ (Scale first, then Rotate)

1. Start with the vector $x = (1, 2)^T$.
2. **Scale horizontally ($S$):** The horizontal coordinate is doubled: $(1, 2) \to (2, 2)$.
3. **Rotate $90^\circ$ counterclockwise ($R$):** The vector $(2, 2)$ rotates into the second quadrant: $(-2, 2)$.
   - The stretched horizontal component ($2$) swings onto the vertical axis ($+2$).
   - The original vertical component ($2$) swings onto the negative horizontal axis ($-2$).

### Path 2: $SRx$ (Rotate first, then Scale)

1. Start with the vector $x = (1, 2)^T$.
2. **Rotate $90^\circ$ counterclockwise ($R$):** The vector rotates to $(-2, 1)$.
   - Notice: what used to be the vertical component ($2$) is now on the horizontal axis (as $-2$).
3. **Scale horizontally ($S$):** The matrix $S$ scales along the **fixed spatial $x$-axis**. It doubles whichever value is currently horizontal:
   - The current horizontal coordinate $-2$ is doubled to $-4$.
   - The vertical coordinate $1$ remains unchanged.
   - Result: $(-4, 1)^T$.

### The Core Reason

The scaling matrix $S$ stretches along the **fixed coordinate $x$-axis**, not along the body axis of the vector.

- In $RS$, scaling happens **before** rotation, so $S$ stretches the original horizontal component ($1 \to 2$).
- In $SR$, rotation happens **first**, swapping the roles of the coordinates before scaling. Therefore, $S$ ends up stretching what was originally the vertical component ($2 \to 4$).

Because rotation changes which part of the vector aligns with the horizontal axis, the two operations cannot commute.

---

## Verification and Consistency Checks

### Determinants (Area Scaling Factor)

The determinant of a $2 \times 2$ matrix gives the factor by which areas are scaled:

$$
\det(S) = (2)(1) - (0)(0) = 2, \qquad \det(R) = (0)(0) - (-1)(1) = 1
$$

Using $\det(AB) = \det(A)\det(B)$:

$$
\det(RS) = \det(R)\det(S) = 1 \cdot 2 = 2
$$

$$
\det(SR) = \det(S)\det(R) = 2 \cdot 1 = 2
$$

Both composite transformations double the area of any region in the plane. Even though individual vectors land in different locations ($RSx \neq SRx$), the area dilation factor is identical. ✅

### Vector Lengths

- Initial length: $\Vert x \Vert = \sqrt{1^2 + 2^2} = \sqrt{5} \approx 2.236$
- Length of $RSx$: $\Vert RSx \Vert = \sqrt{(-2)^2 + 2^2} = \sqrt{8} \approx 2.828$
- Length of $SRx$: $\Vert SRx \Vert = \sqrt{(-4)^2 + 1^2} = \sqrt{17} \approx 4.123$

The lengths are different, further confirming that $RSx \neq SRx$.

---

## Why This Exercise Matters

- **Geometric reality of noncommutativity:** In algebra, $AB \neq BA$ can feel like an arbitrary rule. In geometry, it is intuitive: stretching and then rotating produces a completely different orientation and shape than rotating and then stretching.
- **Computer graphics and game engines:** Every 3D engine multiplies transformation matrices in a strict order (typically Scale, then Rotate, then Translate: $M = T \cdot R \cdot S$). Reversing rotation and scaling distorts the 3D model along the world axes rather than the model's own local axes.
- **Robotics and Kinematics:** Robotic arms rotate and extend limbs. Calculating where the hand lands requires multiplying joint transformation matrices in exact sequence.
