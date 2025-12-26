#Math #NT

# Statement

Let $x \in \mathbb{Z}$, $y \in \mathbb{Z}$, $x \neq 0$, $y \neq 0$, and $g = \gcd(x, y)$. Bezout's Identity states that $\alpha \in \mathbb{Z}$ and $\beta \in \mathbb{Z}$ exists when:

$$
\alpha x + \beta y = g
$$

Furthermore, $g$ is the least positive integer able to be expressed in this form.

# Proof

## First Statement

Let $x = gx_1$ and $y = gy_1$, and notice $\gcd(x_1, y_1) = 1$ and $\operatorname{lcm} (x_1, y_1) = x_1 y_1$.

Since this is true, the smallest integer $\alpha$ for $\alpha x_1 \equiv 0 \mod y$ is $a = y_1$.

For all integers $0 \leq a, b < y_1$, $ax_1 \not\equiv bx_1 \mod y$. (If not, we get $|b - a| > y_1$, which is contradictory). Thus, by pigeonhole principle, there exists $\alpha$ such that $\alpha x_1 \equiv 1 \mod y_1$.

Therefore, there is an $\alpha$ such that $ax_1 - 1 \equiv 0 \mod y_1$, and by extension, there exists an integer $\beta$ such that:

$$
\alpha x_1 - 1 = -\beta y_1 \\
\alpha x_1 + \beta y_1 = 1
$$

By multiplying by $g$:

$$
\alpha x + \beta y = g
$$

## Second Statement

To prove $g$ is minimum, let’s consider another positive integer $g\prime$:

$$
\alpha\prime x + \beta\prime y = g\prime
$$

Since all values are a multiple of $g$:

$$
0 \equiv \alpha \prime x + \beta \prime x \mod g \\
0 \equiv g\prime \mod g
$$

Since $g$ and $g\prime$ are positive integers, $g\prime \geq g$.