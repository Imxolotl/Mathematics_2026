# Problem 9: Distances

## Question

Compute:

1. the distance from $P=(2,3)$ to the line $3x+4y-10=0$,
2. the distance from $Q=(2,-1,3)$ to the plane $2x-2y+z-4=0$.

Compare the two formulas and explain their common connection with the normal direction.

---

## Solution

### 1. Distance from $P = (2, 3)$ to the Line $3x + 4y - 10 = 0$

#### Formula (Point to a Line in $\mathbb{R}^2$):
For a line $L: Ax + By + C = 0$ with normal vector $n = (A, B)$ and a point $P = (x_0, y_0)$, the perpendicular distance is:

$$
d(P, L) = \frac{|Ax_0 + By_0 + C|}{\sqrt{A^2 + B^2}} = \frac{|n \cdot P + C|}{\|n\|}
$$

#### Calculation:
Here $A = 3$, $B = 4$, $C = -10$, so the normal vector is $n = (3, 4)$ and the point is $P = (2, 3)$:

1. **Evaluate the numerator $|Ax_0 + By_0 + C|$:**

$$
|3(2) + 4(3) - 10| = |6 + 12 - 10| = |8| = 8
$$

2. **Compute the length of the normal vector $\|n\|$:**

$$
\|n\| = \sqrt{3^2 + 4^2} = \sqrt{9 + 16} = \sqrt{25} = 5
$$

3. **Divide to obtain the distance:**

$$
d(P, L) = \frac{8}{5} = 1.6
$$

---

### 2. Distance from $Q = (2, -1, 3)$ to the Plane $2x - 2y + z - 4 = 0$

#### Formula (Point to a Plane in $\mathbb{R}^3$):
For a plane $\Pi: Ax + By + Cz + D = 0$ with normal vector $n = (A, B, C)$ and a point $Q = (x_0, y_0, z_0)$, the perpendicular distance is:

$$
d(Q, \Pi) = \frac{|Ax_0 + By_0 + Cz_0 + D|}{\sqrt{A^2 + B^2 + C^2}} = \frac{|n \cdot Q + D|}{\|n\|}
$$

#### Calculation:
Here $A = 2$, $B = -2$, $C = 1$, $D = -4$, so the normal vector is $n = (2, -2, 1)$ and the point is $Q = (2, -1, 3)$:

1. **Evaluate the numerator $|Ax_0 + By_0 + Cz_0 + D|$:**

$$
|2(2) + (-2)(-1) + 1(3) - 4| = |4 + 2 + 3 - 4| = |5| = 5
$$

2. **Compute the length of the normal vector $\|n\|$:**

$$
\|n\| = \sqrt{2^2 + (-2)^2 + 1^2} = \sqrt{4 + 4 + 1} = \sqrt{9} = 3
$$

3. **Divide to obtain the distance:**

$$
d(Q, \Pi) = \frac{5}{3} \approx 1.667
$$

---

### 3. Comparison of the Two Formulas and Connection with the Normal Direction

#### 1. Identical Vector Structure
Both formulas are instances of a single universal vector formula for the distance from a point $X_0$ to a hyperplane $\mathcal{H}: n \cdot X + c = 0$:

$$
d(X_0, \mathcal{H}) = \frac{|n \cdot X_0 + c|}{\|n\|}
$$

- In $\mathbb{R}^2$, the hyperplane is a **line** with $n = (A, B)$ and $\|n\| = \sqrt{A^2 + B^2}$.
- In $\mathbb{R}^3$, the hyperplane is a **plane** with $n = (A, B, C)$ and $\|n\| = \sqrt{A^2 + B^2 + C^2}$.

#### 2. Geometric Derivation via Orthogonal Projection onto the Normal Vector
Why do both formulas evaluate the equation at the point and divide by $\|n\|$?
- Pick any reference point $X_1$ lying on the line or plane. Because $X_1$ satisfies the equation, we have $n \cdot X_1 + c = 0$, or $c = -n \cdot X_1$.
- Form the vector $\overrightarrow{X_1 X_0} = X_0 - X_1$ from the reference point on the line/plane to the external point $X_0$.
- The shortest path from $X_0$ to the line or plane is perpendicular to it — that is, **parallel to the normal vector $n$**.
- Therefore, the shortest distance $d$ is the magnitude of the **orthogonal projection** of $\overrightarrow{X_1 X_0}$ onto the normal direction $n$:

$$
\begin{aligned}
d &= \|\mathrm{proj}_n\,\overrightarrow{X_1 X_0}\| \\
  &= \frac{|n \cdot (X_0 - X_1)|}{\|n\|} \\
  &= \frac{|n \cdot X_0 - n \cdot X_1|}{\|n\|} \\
  &= \frac{|n \cdot X_0 + c|}{\|n\|}
\end{aligned}
$$

- **Role of the Denominator $\|n\|$:** Multiplying a line or plane equation by a constant (e.g., $6x + 8y - 20 = 0$) doubles the numerator $|n \cdot X_0 + c|$ without moving the geometric line at all. Dividing by $\|n\|$ normalizes $n$ into the **unit normal vector** $e_n = \frac{n}{\|n\|}$, ensuring the distance is measured in true Euclidean units.

---

## Verification and Consistency Checks

### Check 1: Foot of the Perpendicular for Part 1

Moving from $P = (2, 3)$ along the normal $n = (3, 4)$ to the line $3x + 4y - 10 = 0$:
The foot of the perpendicular is $P_{\perp} = P - \frac{n \cdot P + C}{\|n\|^2} n$:

$$
P_{\perp} = (2, 3) - \frac{8}{25}(3, 4) = \left( \frac{50 - 24}{25}, \; \frac{75 - 32}{25} \right) = \left( \frac{26}{25}, \; \frac{43}{25} \right)
$$

- Check that $P_{\perp}$ lies on $3x + 4y - 10 = 0$:

$$
3\left(\frac{26}{25}\right) + 4\left(\frac{43}{25}\right) - 10 = \frac{78 + 172}{25} - 10 = \frac{250}{25} - 10 = 10 - 10 = 0
$$

- Distance $\|P - P_{\perp}\| = \left\| \frac{8}{25}(3, 4) \right\| = \frac{8}{25} \cdot 5 = \frac{8}{5}$.

### Check 2: Foot of the Perpendicular for Part 2

Similarly, the closest point on the plane $2x - 2y + z - 4 = 0$ to $Q = (2, -1, 3)$ is:

$$
Q_{\perp} = (2, -1, 3) - \frac{5}{9}(2, -2, 1) = \left( \frac{8}{9}, \; \frac{1}{9}, \; \frac{22}{9} \right)
$$

- Check that $Q_{\perp}$ lies on $2x - 2y + z - 4 = 0$:

$$
2\left(\frac{8}{9}\right) - 2\left(\frac{1}{9}\right) + \frac{22}{9} - 4 = \frac{16 - 2 + 22}{9} - 4 = \frac{36}{9} - 4 = 4 - 4 = 0
$$

- Distance $\|Q - Q_{\perp}\| = \left\| \frac{5}{9}(2, -2, 1) \right\| = \frac{5}{9} \cdot 3 = \frac{5}{3}$.

---

## Why This Exercise Matters

- **One Concept Instead of Two Formulas:** Recognizing that both formulas simply project a displacement vector onto the unit normal $e_n = \frac{n}{\|n\|}$ eliminates rote memorization.
- **Scale Invariance:** Dividing by $\|n\|$ guarantees that equivalent equations for the same line or plane always yield the exact same geometric distance.
