#Math #Algebra

A matrix is an $n$ by $m$ set of values. A $4 \times 3$can be notated by:

$$
\begin{bmatrix}a_1 & a_2 & a_3 \cr b_1 & b_2 & b_3 \cr c_1 & c_2 & c_3 \cr d_1 & d_2 & d_3 \end{bmatrix}
$$

To get a value from matrix $a$ in row $r$ and column $c$, use:

$$
a_{r, c}
$$

# Addition

With two matrices of the same order, add corresponding elements:

$$
\begin{bmatrix} a_1 & b_1 \cr c_1 & d_1 \end{bmatrix} + \begin{bmatrix} a_2 & b_2 \cr c_2 & d_2 \end{bmatrix} = \begin{bmatrix} a_1 + a_2 & b_1 + b_2 \cr c_1 + c_2 & d_1 + d_2 \end{bmatrix}
$$

# Subtraction

With two matrices of the same order, subtract corresponding elements:

$$
\begin{bmatrix} a_1 & b_1 \cr c_1 & d_1 \end{bmatrix} - \begin{bmatrix} a_2 & b_2 \cr c_2 & d_2 \end{bmatrix} = \begin{bmatrix} a_1 - a_2 & b_1 - b_2 \cr c_1 - c_2 & d_1 - d_2 \end{bmatrix}
$$

# Scalar Multiplication

When multiplying a matrix by a scalar, multiply each element by said scalar:

$$
s\begin{bmatrix} a & b \cr c & d \end{bmatrix} = \begin{bmatrix} sa & sb \cr sc & sd \end{bmatrix}
$$

# Matrix Multiplication

Let $a$ be an $i$ by $j$ matrix and $b$ be a $m$ by $n$ matrix. If $j = m$, $ab$ is defined.

$$
ab_{c, d} = \sum _{k = 1}^{j} a_{c, k}b_{k, d}
$$