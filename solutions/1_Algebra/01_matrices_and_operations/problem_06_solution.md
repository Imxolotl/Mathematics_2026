# Problem 6: Transpose

## Question

Given the matrices

$$
A = \begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{pmatrix}, \qquad
B = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix},
$$

compute $A^T$, $B^T$, and $AB$. Then verify in this example that

$$
(AB)^T = B^T A^T.
$$

---

## Key Rule — What Is a Transpose?

The **transpose** of a matrix is obtained by **turning its rows into columns** (equivalently, turning its columns into rows). We write it as $A^T$.

Formally, if $A$ is an $m \times n$ matrix with entry $a_{ij}$ in row $i$, column $j$, then $A^T$ is the $n \times m$ matrix whose entry in row $j$, column $i$ is that same $a_{ij}$:

$$
(A^T)_{ji} = a_{ij}.
$$

A quick way to picture it: **reflect the matrix across its main diagonal** (the line from top-left to bottom-right). Rows become columns and the shape flips — an $m \times n$ matrix becomes $n \times m$.

---

## Step 1 — Compute $A^T$

$A$ is $2 \times 3$, so $A^T$ will be $3 \times 2$.

Row 1 of $A$ becomes column 1 of $A^T$; row 2 of $A$ becomes column 2 of $A^T$:

$$
A = \begin{pmatrix} 1 & 2 & 3 \\ 4 & 5 & 6 \end{pmatrix}
\qquad \Longrightarrow \qquad
A^T = \begin{pmatrix} 1 & 4 \\ 2 & 5 \\ 3 & 6 \end{pmatrix}.
$$

Check a few entries to be sure:

- $a_{12} = 2$ should appear at position $(2, 1)$ of $A^T$. It does. ✅
- $a_{23} = 6$ should appear at position $(3, 2)$ of $A^T$. It does. ✅

---

## Step 2 — Compute $B^T$

$B$ is $3 \times 2$, so $B^T$ will be $2 \times 3$.

$$
B = \begin{pmatrix} 1 & 0 \\ 2 & 1 \\ -1 & 3 \end{pmatrix}
\qquad \Longrightarrow \qquad
B^T = \begin{pmatrix} 1 & 2 & -1 \\ 0 & 1 & 3 \end{pmatrix}.
$$

---

## Step 3 — Compute $AB$

$A$ is $2 \times 3$ and $B$ is $3 \times 2$. The inner dimensions match ($3 = 3$), so the product is defined and will be $2 \times 2$.

### Entry (1, 1): row 1 of $A$ · column 1 of $B$

$$
\begin{pmatrix} 1 & 2 & 3 \end{pmatrix}
\cdot
\begin{pmatrix} 1 \\ 2 \\ -1 \end{pmatrix}
= 1 \cdot 1 + 2 \cdot 2 + 3 \cdot (-1) = 1 + 4 - 3 = 2.
$$

### Entry (1, 2): row 1 of $A$ · column 2 of $B$

$$
\begin{pmatrix} 1 & 2 & 3 \end{pmatrix}
\cdot
\begin{pmatrix} 0 \\ 1 \\ 3 \end{pmatrix}
= 1 \cdot 0 + 2 \cdot 1 + 3 \cdot 3 = 0 + 2 + 9 = 11.
$$

### Entry (2, 1): row 2 of $A$ · column 1 of $B$

$$
\begin{pmatrix} 4 & 5 & 6 \end{pmatrix}
\cdot
\begin{pmatrix} 1 \\ 2 \\ -1 \end{pmatrix}
= 4 \cdot 1 + 5 \cdot 2 + 6 \cdot (-1) = 4 + 10 - 6 = 8.
$$

### Entry (2, 2): row 2 of $A$ · column 2 of $B$

$$
\begin{pmatrix} 4 & 5 & 6 \end{pmatrix}
\cdot
\begin{pmatrix} 0 \\ 1 \\ 3 \end{pmatrix}
= 4 \cdot 0 + 5 \cdot 1 + 6 \cdot 3 = 0 + 5 + 18 = 23.
$$

### Result

$$
AB = \begin{pmatrix} 2 & 11 \\ 8 & 23 \end{pmatrix}.
$$

---

## Step 4 — Compute $(AB)^T$

$AB$ is $2 \times 2$, so $(AB)^T$ is also $2 \times 2$. We just swap rows and columns (or equivalently, reflect across the diagonal):

$$
(AB)^T = \begin{pmatrix} 2 & 8 \\ 11 & 23 \end{pmatrix}.
$$

Notice that the diagonal entries ($2$ and $23$) stay in place, while the off-diagonal entries ($11$ and $8$) swap positions.

---

## Step 5 — Compute $B^T A^T$ and Verify the Identity

### Why $B^T A^T$ and not $A^T B^T$?

The transpose rule **reverses the order** of the factors. This is crucial and easy to mix up. The claim is:

$$
(AB)^T = B^T A^T \qquad (\text{note: } B \text{ comes first!}).
$$

### Check that the sizes work

- $B^T$ is $2 \times 3$ and $A^T$ is $3 \times 2$. The inner dimensions match ($3 = 3$), so the product $B^T A^T$ is defined and is $2 \times 2$. ✅
- Had we tried $A^T B^T$ instead ($3 \times 2$ times $2 \times 3$), we would get a $3 \times 3$ matrix — that cannot possibly equal $(AB)^T$, which is $2 \times 2$.

### Compute entry by entry

#### Entry (1, 1): row 1 of $B^T$ · column 1 of $A^T$

$$
\begin{pmatrix} 1 & 2 & -1 \end{pmatrix}
\cdot
\begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}
= 1 \cdot 1 + 2 \cdot 2 + (-1) \cdot 3 = 1 + 4 - 3 = 2.
$$

#### Entry (1, 2): row 1 of $B^T$ · column 2 of $A^T$

$$
\begin{pmatrix} 1 & 2 & -1 \end{pmatrix}
\cdot
\begin{pmatrix} 4 \\ 5 \\ 6 \end{pmatrix}
= 1 \cdot 4 + 2 \cdot 5 + (-1) \cdot 6 = 4 + 10 - 6 = 8.
$$

#### Entry (2, 1): row 2 of $B^T$ · column 1 of $A^T$

$$
\begin{pmatrix} 0 & 1 & 3 \end{pmatrix}
\cdot
\begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}
= 0 \cdot 1 + 1 \cdot 2 + 3 \cdot 3 = 0 + 2 + 9 = 11.
$$

#### Entry (2, 2): row 2 of $B^T$ · column 2 of $A^T$

$$
\begin{pmatrix} 0 & 1 & 3 \end{pmatrix}
\cdot
\begin{pmatrix} 4 \\ 5 \\ 6 \end{pmatrix}
= 0 \cdot 4 + 1 \cdot 5 + 3 \cdot 6 = 0 + 5 + 18 = 23.
$$

### Result

$$
B^T A^T = \begin{pmatrix} 2 & 8 \\ 11 & 23 \end{pmatrix}.
$$

### Comparison

$$
(AB)^T = \begin{pmatrix} 2 & 8 \\ 11 & 23 \end{pmatrix}, \qquad
B^T A^T = \begin{pmatrix} 2 & 8 \\ 11 & 23 \end{pmatrix}.
$$

Every entry matches:

$$
(AB)^T = B^T A^T.
$$

✅ **Verified.**

---

## Step 6 — Why Does the Order Reverse?

This is the part worth understanding, not just memorizing.

### The intuition

Think of the product $AB$ as a two-step pipeline: apply $B$ first, then apply $A$ (right-to-left, the way matrix multiplication acts on a vector: $A(B\mathbf{x})$).

Transposing is like **looking at everything from the other side of the mirror** — it flips rows and columns. When you flip the whole pipeline, the steps come out in **reverse order**, just like taking off shoes and socks: you put socks on first and shoes second, but you take shoes off first and socks second.

So $(AB)^T$ reverses the order: $B^T$ first, then $A^T$.

### A sketch of the general proof

For any $m \times n$ matrix $A$ and $n \times p$ matrix $B$, the entry in row $i$, column $j$ of $(AB)^T$ is:

$$
\left((AB)^T\right)_{ij} = (AB)_{ji} = \sum_{k=1}^{n} a_{jk} \, b_{ki}.
$$

The entry in row $i$, column $j$ of $B^T A^T$ is:

$$
(B^T A^T)_{ij} = \sum_{k=1}^{n} (B^T)_{ik} \, (A^T)_{kj} = \sum_{k=1}^{n} b_{ki} \, a_{jk}.
$$

Since ordinary number multiplication is commutative ($a_{jk} \cdot b_{ki} = b_{ki} \cdot a_{jk}$), the two sums are identical. The identity holds for **all** matrices of compatible sizes, not just this example.

---

## Summary of Transpose Properties

This exercise demonstrates one rule, but here is the full family for reference:

| Property | Formula |
|:---------|:--------|
| Double transpose | $(A^T)^T = A$ |
| Transpose of a sum | $(A + B)^T = A^T + B^T$ |
| Scalar factor | $(cA)^T = c \, A^T$ |
| **Transpose of a product** | $(AB)^T = B^T A^T$ |
| Three or more factors | $(ABC)^T = C^T B^T A^T$ |

The product rule is the only one that **reverses the order**. The others keep the order or involve only one matrix.

---

## Why This Exercise Matters

- **Transposition is one of the most common operations** you will perform on matrices, right alongside addition, scaling, and multiplication. Every time you work with symmetric matrices, orthogonal matrices, or least-squares problems, transposes appear.
- **The reversal rule $(AB)^T = B^T A^T$ prevents a very common mistake.** Many students instinctively write $A^T B^T$ — this exercise forces you to see, with concrete numbers, why that is wrong and why the reversed order is correct.
- **Sizes tell the story.** Even before computing, we saw that $A^T B^T$ would be $3 \times 3$ while $(AB)^T$ is $2 \times 2$, so the wrong order cannot even produce a matrix of the right shape. Checking sizes first is a powerful habit.
- **Foundation for deeper topics.** The transpose reversal rule reappears with inverses ($(AB)^{-1} = B^{-1}A^{-1}$) and in many other settings. Getting comfortable with it now pays off later.

