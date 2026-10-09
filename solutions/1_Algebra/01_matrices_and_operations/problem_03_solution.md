# Problem 3: When Can Matrices Be Multiplied?

## Question

The matrix sizes are

$$
A_{2\times3},\qquad B_{3\times4},\qquad C_{4\times2},\qquad D_{2\times2}.
$$

For the products

$$
AB,\ BA,\ BC,\ CB,\ AC,\ CA,\ AD,\ DA
$$

determine whether they are defined. If so, state the size of the result. Justify each decision using the dimension compatibility condition.

---

## Key Rule — The Dimension Compatibility Condition

Before working through each product, here is the rule we apply every time.

To multiply two matrices, the **number of columns of the left matrix** must equal the **number of rows of the right matrix**.

If the left matrix has size $m \times \mathbf{n}$ and the right matrix has size $\mathbf{n} \times p$, then:

- the product **is defined**, because the shared dimension $n$ matches,
- the result has size $m \times p$.

If those inner dimensions do not match, the product **is not defined** — it simply does not exist.

A helpful way to visualise this:

$$
\underbrace{(\,m \times \mathbf{n}\,)}_{\text{left}}
\;\cdot\;
\underbrace{(\,\mathbf{n} \times p\,)}_{\text{right}}
\;=\;
(\,m \times p\,)
$$

The two **bold** numbers in the middle must be equal. If they are, the outer numbers $m$ and $p$ give the size of the result.

---

## Given Sizes

| Matrix | Rows | Columns | Size |
|:------:|:----:|:-------:|:----:|
| $A$    | 2    | 3       | $2 \times 3$ |
| $B$    | 3    | 4       | $3 \times 4$ |
| $C$    | 4    | 2       | $4 \times 2$ |
| $D$    | 2    | 2       | $2 \times 2$ |

---

## Analysis of Each Product

### 1. Product $AB$

- Left matrix $A$: size $2 \times \mathbf{3}$.
- Right matrix $B$: size $\mathbf{3} \times 4$.
- Inner dimensions: $\mathbf{3} = \mathbf{3}$. ✅ **Match.**

$A$ has 3 columns and $B$ has 3 rows, so every row of $A$ can be paired with every column of $B$ to compute a dot product. The product is defined.

$$
AB \text{ is defined, result size: } 2 \times 4.
$$

---

### 2. Product $BA$

- Left matrix $B$: size $3 \times \mathbf{4}$.
- Right matrix $A$: size $\mathbf{2} \times 3$.
- Inner dimensions: $\mathbf{4} \neq \mathbf{2}$. ❌ **No match.**

$B$ has 4 columns but $A$ has only 2 rows. There is no way to pair a 4-entry row of $B$ with a 2-entry column of $A$ — they have different lengths, so the dot product is undefined.

$$
BA \text{ is \textbf{not defined}.}
$$

> **Note:** This already shows that matrix multiplication is not commutative: $AB$ exists, but $BA$ does not.

---

### 3. Product $BC$

- Left matrix $B$: size $3 \times \mathbf{4}$.
- Right matrix $C$: size $\mathbf{4} \times 2$.
- Inner dimensions: $\mathbf{4} = \mathbf{4}$. ✅ **Match.**

Each row of $B$ has 4 entries and each column of $C$ has 4 entries, so the dot products are well-defined.

$$
BC \text{ is defined, result size: } 3 \times 2.
$$

---

### 4. Product $CB$

- Left matrix $C$: size $4 \times \mathbf{2}$.
- Right matrix $B$: size $\mathbf{3} \times 4$.
- Inner dimensions: $\mathbf{2} \neq \mathbf{3}$. ❌ **No match.**

$C$ has 2 columns, $B$ has 3 rows. A 2-entry row of $C$ cannot be dotted with a 3-entry column of $B$.

$$
CB \text{ is \textbf{not defined}.}
$$

---

### 5. Product $AC$

- Left matrix $A$: size $2 \times \mathbf{3}$.
- Right matrix $C$: size $\mathbf{4} \times 2$.
- Inner dimensions: $\mathbf{3} \neq \mathbf{4}$. ❌ **No match.**

$A$ has 3 columns, $C$ has 4 rows. The lengths don't match, so there is no valid dot product.

$$
AC \text{ is \textbf{not defined}.}
$$

---

### 6. Product $CA$

- Left matrix $C$: size $4 \times \mathbf{2}$.
- Right matrix $A$: size $\mathbf{2} \times 3$.
- Inner dimensions: $\mathbf{2} = \mathbf{2}$. ✅ **Match.**

Each row of $C$ has 2 entries, each column of $A$ has 2 entries. The dot products work.

$$
CA \text{ is defined, result size: } 4 \times 3.
$$

---

### 7. Product $AD$

- Left matrix $A$: size $2 \times \mathbf{3}$.
- Right matrix $D$: size $\mathbf{2} \times 2$.
- Inner dimensions: $\mathbf{3} \neq \mathbf{2}$. ❌ **No match.**

$A$ has 3 columns, $D$ has only 2 rows. No valid pairing exists.

$$
AD \text{ is \textbf{not defined}.}
$$

---

### 8. Product $DA$

- Left matrix $D$: size $2 \times \mathbf{2}$.
- Right matrix $A$: size $\mathbf{2} \times 3$.
- Inner dimensions: $\mathbf{2} = \mathbf{2}$. ✅ **Match.**

$D$ has 2 columns and $A$ has 2 rows. Each pair lines up for a dot product.

$$
DA \text{ is defined, result size: } 2 \times 3.
$$

---

## Summary Table

| Product | Left size | Right size | Inner dims | Defined? | Result size |
|:-------:|:---------:|:----------:|:----------:|:--------:|:-----------:|
| $AB$    | $2\times3$ | $3\times4$ | $3 = 3$ | ✅ Yes | $2\times4$ |
| $BA$    | $3\times4$ | $2\times3$ | $4 \neq 2$ | ❌ No | — |
| $BC$    | $3\times4$ | $4\times2$ | $4 = 4$ | ✅ Yes | $3\times2$ |
| $CB$    | $4\times2$ | $3\times4$ | $2 \neq 3$ | ❌ No | — |
| $AC$    | $2\times3$ | $4\times2$ | $3 \neq 4$ | ❌ No | — |
| $CA$    | $4\times2$ | $2\times3$ | $2 = 2$ | ✅ Yes | $4\times3$ |
| $AD$    | $2\times3$ | $2\times2$ | $3 \neq 2$ | ❌ No | — |
| $DA$    | $2\times2$ | $2\times3$ | $2 = 2$ | ✅ Yes | $2\times3$ |

**Score: 4 defined, 4 not defined.**

---

## Verification and Consistency Checks

1. **Symmetry is not guaranteed:**
   Of the four pairs where both orders were tested ($AB$ vs $BA$, $BC$ vs $CB$, $AC$ vs $CA$, $AD$ vs $DA$), in every case exactly one order was defined and the other was not. This confirms that swapping the order of multiplication generally changes whether the product exists at all.

2. **Resulting sizes are consistent with the rule:**
   In each defined product, the result size equals (rows of left matrix) $\times$ (columns of right matrix):
   - $AB$: $2 \times 4$ — takes its 2 rows from $A$ and its 4 columns from $B$.
   - $BC$: $3 \times 2$ — takes its 3 rows from $B$ and its 2 columns from $C$.
   - $CA$: $4 \times 3$ — takes its 4 rows from $C$ and its 3 columns from $A$.
   - $DA$: $2 \times 3$ — takes its 2 rows from $D$ and its 3 columns from $A$.

3. **Chain check — $A \cdot B \cdot C$:**
   Since $AB$ is $2 \times 4$ and $C$ is $4 \times 2$, the triple product $(AB)C$ would also be defined, giving a $2 \times 2$ result. This is consistent: each link in the chain has compatible inner dimensions.

---

## Why This Exercise Matters

- **Dimension check before calculation:** In practice, verifying dimensions is always the first step before attempting any matrix multiplication. Skipping this check leads to wasted effort or meaningless results.
- **Noncommutativity at the deepest level:** With numbers, if $a \cdot b$ exists then $b \cdot a$ also exists and gives the same result. With matrices, the reversed product may not even be defined — not just different, but nonexistent. This is a stronger form of noncommutativity than what Exercise 4 will explore.
- **Reading the result size:** The outer-dimensions rule ($m \times p$) is worth memorising, because it tells you the shape of every intermediate result when you chain several matrix multiplications together.

