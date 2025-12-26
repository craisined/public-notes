#Math #Probability

# Statement

For $n \geq r$, $n, r \in \mathbb{N}$:

$$
\sum _{i = r}^n {i \choose r} = {n + 1 \choose r + 1}
$$

# Proof

Let us have a base case $n = r$:

$$
{r \choose r} = {r + 1 \choose r + 1} = 1
$$

Now suppose $\sum _{i = r}^n {i \choose r} = {n + 1 \choose r + 1}$ for a certain $n$:

$$
\sum _{i = r}^n {i \choose r} + {n + 1 \choose r} \\
= {n + 1 \choose r + 1} + {n + 1 \choose r} \\
= {n + 2 \choose r + 1}
$$

Since $n = r$ is true, and if a case is true for $n$, it is true for $n + 1$, this statement is true for all $n \geq r$.