# Problem 4: Matrix Multiplication and Noncommutativity

## Question

Given the $2 \times 2$ matrices

$$
A = \begin{pmatrix} 1 & 2 \\ 0 & 1 \end{pmatrix}, \qquad
B = \begin{pmatrix} 2 & 0 \\ 3 & 1 \end{pmatrix},
$$

compute $AB$ and $BA$. Is $AB = BA$? Use this example to explain what **noncommutativity** of matrix multiplication means.

---

## Key Rule — How to Multiply Two $2 \times 2$ Matrices

For two $2 \times 2$ matrices

$$
X = \begin{pmatrix} x_{11} & x_{12} \\ x_{21} & x_{22} \end{pmatrix}, \qquad
Y = \begin{pmatrix} y_{11} & y_{12} \\ y_{21} & y_{22} \end{pmatrix},
$$

the product $XY$ is computed by taking **dot products of rows of $X$ with columns of $Y$**:

$$
XY = \begin{pmatrix}
x_{11}\,y_{11} + x_{12}\,y_{21} & x_{11}\,y_{12} + x_{12}\,y_{22} \\
x_{21}\,y_{11} + x_{22}\,y_{21} & x_{21}\,y_{12} + x_{22}\,y_{22}
\end{pmatrix}.
$$

In words: to find the entry in **row $i$, column $j$** of the product, take the $i$-th row of the left matrix and the $j$-th column of the right matrix, multiply their corresponding entries together, and add up the results.

---

## Step 1 — Compute $AB$

We need each of the four entries of the $2 \times 2$ result.

### Entry (1, 1): row 1 of $A$ · column 1 of $B$

$$
\begin{pmatrix} 1 & 2 \end{pmatrix}
\cdot
\begin{pmatrix} 2 \\ 3 \end{pmatrix}
= 1 \cdot 2 + 2 \cdot 3 = 2 + 6 = 8.
$$

### Entry (1, 2): row 1 of $A$ · column 2 of $B$

$$
\begin{pmatrix} 1 & 2 \end{pmatrix}
\cdot
\begin{pmatrix} 0 \\ 1 \end{pmatrix}
= 1 \cdot 0 + 2 \cdot 1 = 0 + 2 = 2.
$$

### Entry (2, 1): row 2 of $A$ · column 1 of $B$

$$
\begin{pmatrix} 0 & 1 \end{pmatrix}
\cdot
\begin{pmatrix} 2 \\ 3 \end{pmatrix}
= 0 \cdot 2 + 1 \cdot 3 = 0 + 3 = 3.
$$

### Entry (2, 2): row 2 of $A$ · column 2 of $B$

$$
\begin{pmatrix} 0 & 1 \end{pmatrix}
\cdot
\begin{pmatrix} 0 \\ 1 \end{pmatrix}
= 0 \cdot 0 + 1 \cdot 1 = 0 + 1 = 1.
$$

### Result

$$
AB = \begin{pmatrix} 8 & 2 \\ 3 & 1 \end{pmatrix}.
$$

---

## Step 2 — Compute $BA$

Now $B$ is on the left and $A$ is on the right. We repeat exactly the same process, but take rows of $B$ and columns of $A$.

### Entry (1, 1): row 1 of $B$ · column 1 of $A$

$$
\begin{pmatrix} 2 & 0 \end{pmatrix}
\cdot
\begin{pmatrix} 1 \\ 0 \end{pmatrix}
= 2 \cdot 1 + 0 \cdot 0 = 2 + 0 = 2.
$$

### Entry (1, 2): row 1 of $B$ · column 2 of $A$

$$
\begin{pmatrix} 2 & 0 \end{pmatrix}
\cdot
\begin{pmatrix} 2 \\ 1 \end{pmatrix}
= 2 \cdot 2 + 0 \cdot 1 = 4 + 0 = 4.
$$

### Entry (2, 1): row 2 of $B$ · column 1 of $A$

$$
\begin{pmatrix} 3 & 1 \end{pmatrix}
\cdot
\begin{pmatrix} 1 \\ 0 \end{pmatrix}
= 3 \cdot 1 + 1 \cdot 0 = 3 + 0 = 3.
$$

### Entry (2, 2): row 2 of $B$ · column 2 of $A$

$$
\begin{pmatrix} 3 & 1 \end{pmatrix}
\cdot
\begin{pmatrix} 2 \\ 1 \end{pmatrix}
= 3 \cdot 2 + 1 \cdot 1 = 6 + 1 = 7.
$$

### Result

$$
BA = \begin{pmatrix} 2 & 4 \\ 3 & 7 \end{pmatrix}.
$$

---

## Step 3 — Compare $AB$ and $BA$

Placing the two results side by side:

$$
AB = \begin{pmatrix} 8 & 2 \\ 3 & 1 \end{pmatrix}, \qquad
BA = \begin{pmatrix} 2 & 4 \\ 3 & 7 \end{pmatrix}.
$$

| Position | $AB$ | $BA$ | Equal? |
|:--------:|:----:|:----:|:------:|
| (1, 1)   | 8    | 2    | ❌     |
| (1, 2)   | 2    | 4    | ❌     |
| (2, 1)   | 3    | 3    | ✅     |
| (2, 2)   | 1    | 7    | ❌     |

Three out of four entries are different. Therefore:

$$
\boxed{AB \neq BA.}
$$

---

## What Does "Noncommutativity" Mean?

### The idea in one sentence

**Noncommutativity** means that the order in which you multiply matters: doing $A$ first and then $B$ gives a different result from doing $B$ first and then $A$.

### Contrast with ordinary numbers

With ordinary numbers, multiplication is **commutative** — the order does not matter:

$$
3 \times 5 = 5 \times 3 = 15.
$$

This is a property we are so used to that we rarely think about it. But with matrices, this property **fails**. We just proved a concrete example: $AB$ and $BA$ are both perfectly well-defined $2 \times 2$ matrices, yet they contain different numbers.

### Why does it fail?

The entry in row $i$, column $j$ of $AB$ is the dot product of **row $i$ of $A$** with **column $j$ of $B$**. When we compute $BA$ instead, the same position uses **row $i$ of $B$** with **column $j$ of $A$** — completely different numbers go into the calculation.

Swapping the order swaps which matrix supplies the rows and which supplies the columns. Since rows and columns of $A$ and $B$ generally contain different numbers, the dot products come out differently.

### What to remember

1. **Never assume $AB = BA$** when working with matrices. Always respect the order.
2. In Problem 3 we saw an even stronger phenomenon: sometimes one order is defined but the reversed order is not even possible (different sizes). Here both orders exist, yet they still differ — this is the subtler form of noncommutativity.
3. There are special cases where $AB = BA$ does hold (for example, when $B$ is the identity matrix, or when $A$ and $B$ are both diagonal matrices). But these are exceptions, not the rule.

---

## Verification

A quick sanity check: both products should have the same **trace** (sum of diagonal entries) only if the matrices happen to satisfy $\text{tr}(AB) = \text{tr}(BA)$. In fact, this trace identity is always true for any square matrices:

$$
\text{tr}(AB) = 8 + 1 = 9, \qquad
\text{tr}(BA) = 2 + 7 = 9. \quad ✅
$$

The traces match, which is consistent with the general theorem $\text{tr}(AB) = \text{tr}(BA)$. This confirms we have not made an arithmetic error, even though the individual entries differ.

---

## Why This Exercise Matters

- **Core difference from number arithmetic:** Noncommutativity is one of the very first things that separates matrix algebra from ordinary algebra. If you only remember one thing about matrix multiplication, it should be: **order matters**.
- **Practical consequence:** In applications (physics, computer graphics, data science), applying transformation $A$ followed by $B$ is **not** the same as applying $B$ followed by $A$. For instance, rotating an object and then scaling it gives a different outcome from scaling it and then rotating it.
- **Foundation for deeper topics:** Understanding noncommutativity prepares you for concepts like commutators ($[A, B] = AB - BA$), which play a central role in quantum mechanics and abstract algebra.

