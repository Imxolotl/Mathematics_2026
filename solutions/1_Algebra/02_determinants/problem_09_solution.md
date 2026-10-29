# Problem 9: Area and the Determinant

## Question

The vectors

$$
u =
\begin{pmatrix}
3 \\
1
\end{pmatrix},\qquad v =
\begin{pmatrix}
1 \\
4
\end{pmatrix}
$$

span a parallelogram. Compute its area using a determinant. Then reverse the order of the vectors and explain what changes in the determinant and what does not change in the area.

---

## Solution

### 1. Geometric Interpretation of the 2x2 Determinant

In $\mathbb{R}^2$, the determinant of a $2 \times 2$ matrix formed by placing two vectors $u$ and $v$ as columns represents the **signed area** of the parallelogram spanned by those vectors:

$$
\det [u \mid v] = \pm \mathrm{Area}
$$

The true geometric area of the parallelogram is given by the absolute value of the determinant:

$$
\mathrm{Area} = |\det [u \mid v]|
$$

The sign of the determinant conveys the **orientation** of the ordered pair $(u, v)$:
- Positive sign ($\det > 0$): the shortest rotation from the first vector $u$ to the second vector $v$ is counterclockwise (positive or right-handed orientation).
- Negative sign ($\det < 0$): the shortest rotation from $u$ to $v$ is clockwise (negative or left-handed orientation).
- Zero ($\det = 0$): the vectors are collinear (linearly dependent), and the parallelogram degenerates into a line segment with area zero.

---

### 2. Area Computation for the Ordered Pair $(u, v)$

Construct the matrix $M$ using $u$ as the first column and $v$ as the second column:

$$
M =
\begin{pmatrix}
3 & 1 \\
1 & 4
\end{pmatrix}
$$

Computing the determinant:

$$
\begin{aligned}
\det M &= (3)(4) - (1)(1) \\
       &= 12 - 1 \\
       &= 11
\end{aligned}
$$

Taking the absolute value gives the area:

$$
\mathrm{Area} = |\det M| = |11| = 11
$$

Since $\det M = 11 > 0$, the ordered pair $(u, v)$ forms a positively oriented (counterclockwise) system.

---

### 3. Reversing the Order of the Vectors: $(v, u)$

Construct the matrix $N$ using $v$ as the first column and $u$ as the second column:

$$
N =
\begin{pmatrix}
1 & 3 \\
4 & 1
\end{pmatrix}
$$

Computing the determinant:

$$
\begin{aligned}
\det N &= (1)(1) - (3)(4) \\
       &= 1 - 12 \\
       &= -11
\end{aligned}
$$

Taking the absolute value gives the area:

$$
\mathrm{Area} = |\det N| = |-11| = 11
$$

---

### 4. Explanation: What Changes and What Does Not Change

#### What Changes: The Sign of the Determinant (Orientation)

- **Algebraic reason:** Swapping the two columns of a matrix interchanges two arguments of an alternating multilinear form, which multiplies the determinant by $-1$:

$$
\det [v \mid u] = -\det [u \mid v]
$$

- **Geometric reason:** Reversing the ordering from $(u, v)$ to $(v, u)$ reverses the spatial orientation in the plane. Turning from $u = (3, 1)$ to $v = (1, 4)$ moves in the counterclockwise direction (angle of $+63.43^\circ$), while turning from $v = (1, 4)$ to $u = (3, 1)$ moves in the clockwise direction (angle of $-63.43^\circ$). The signed determinant changes from $+11$ to $-11$.

#### What Does Not Change: The Area of the Parallelogram (Magnitude)

- **Geometric reason:** The physical parallelogram spanned by $u$ and $v$ has vertices at:

$$
(0, 0), \qquad (3, 1), \qquad (1, 4), \qquad (3+1, 1+4) = (4, 5)
$$

  Reversing the sequence in which the edges are listed does not alter the vertices, the side lengths, the interior angles, or the enclosed two-dimensional region.
- **Mathematical measure:** Geometric area is a non-negative scalar quantity (the two-dimensional Lebesgue measure). Because the absolute value function discards the orientation sign:

$$
|11| = |-11| = 11
$$

  the geometric area remains exactly $11$ in both cases.

---

## Verification and Consistency Checks

1. **Standard Base and Height Geometric Calculation:**
   Take vector $u = (3, 1)$ as the base of the parallelogram.
   - Base length:

$$
b = \|u\| = \sqrt{3^2 + 1^2} = \sqrt{10}
$$

   - Orthogonal projection of $v = (1, 4)$ onto $u$:

$$
\mathrm{proj}_u v = \frac{u \cdot v}{\|u\|^2} u = \frac{(3)(1) + (1)(4)}{10}
\begin{pmatrix}
3 \\
1
\end{pmatrix}
$$

$$
\mathrm{proj}_u v = \frac{7}{10}
\begin{pmatrix}
3 \\
1
\end{pmatrix}
= \begin{pmatrix}
2.1 \\
0.7
\end{pmatrix}
$$

   - Altitude (height) vector orthogonal to $u$:

$$
h_{\mathrm{vec}} = v - \mathrm{proj}_u v =
\begin{pmatrix}
1 - 2.1 \\
4 - 0.7
\end{pmatrix}
= \begin{pmatrix}
-1.1 \\
3.3
\end{pmatrix}
= \frac{11}{10}
\begin{pmatrix}
-1 \\
3
\end{pmatrix}
$$

   - Height length:

$$
h = \|h_{\mathrm{vec}}\| = \frac{11}{10} \sqrt{(-1)^2 + 3^2} = \frac{11}{10} \sqrt{10}
$$

   - Area formula:

$$
\mathrm{Area} = b \cdot h = \sqrt{10} \cdot \left(\frac{11}{10} \sqrt{10}\right) = \frac{11}{10} \cdot 10 = 11
$$

   This matches the determinant result.

2. **Vector Cross Product in $\mathbb{R}^3$:**
   Embedding vectors $u$ and $v$ into the $xy$-plane of $\mathbb{R}^3$:

$$
u = (3, 1, 0), \qquad v = (1, 4, 0)
$$

   The cross product is:

$$
u \times v = (0, 0, (3)(4) - (1)(1)) = (0, 0, 11)
$$

   Its magnitude gives the area:

$$
\|u \times v\| = \sqrt{0^2 + 0^2 + 11^2} = 11
$$

   Reversing the order gives the anti-commutative cross product:

$$
v \times u = -(u \times v) = (0, 0, -11)
$$

   Its magnitude remains $\|v \times u\| = 11$.

3. **Shoelace Formula Check:**
   Traversing vertices $(0,0) \to (3,1) \to (4,5) \to (1,4) \to (0,0)$:

$$
\begin{aligned}
\mathrm{Area} &= \frac{1}{2} |(0 \cdot 1 - 0 \cdot 3) + (3 \cdot 5 - 1 \cdot 4) + (4 \cdot 4 - 5 \cdot 1) + (1 \cdot 0 - 4 \cdot 0)| \\
              &= \frac{1}{2} |0 + (15 - 4) + (16 - 5) + 0| \\
              &= \frac{1}{2} |11 + 11| \\
              &= 11
\end{aligned}
$$

   All three independent methods confirm that the geometric area is $11$.

---

## Why This Exercise Matters

- **The Meaning of Negative Determinants:** Resolves a common source of confusion by distinguishing the geometric magnitude of a region (always positive) from the orientation of coordinate axes (captured by the sign of the determinant).
- **Multivariable Calculus (Jacobian Determinant):** In multiple integration, the change-of-variables formula requires the absolute value of the Jacobian determinant:

$$
\iint_R f(x, y)\,dx\,dy = \iint_S f(u, v) |\det J|\,du\,dv
$$

  The absolute value is necessary because area and volume must be strictly positive measures.
- **Differential Forms:** In higher mathematics and physics, differential forms are inherently antisymmetric ($dx \wedge dy = -dy \wedge dx$). The determinant formalizes the behavior of oriented flux and volume forms in Stokes' theorem.
