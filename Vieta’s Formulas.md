#Math #Algebra

Let polynomial $a$ be:

$$
a = c_n \prod _{i = 0}^n (x - r_i)
$$

where $r_i$ is a root of $a$, and $c_n$ is the leading coefficient of $a$.

We can also represent $a$ as:

$$
a = \sum _{i = 0}^n c_i x^i
$$

By expanding the first definition of $a$, we can define $c_i$ by:

$$
c_{n-i} = (-1)^i c_n\sum _{sym}^i r
$$

This is through the nature of multiplying binomials, with the coefficient resulting in the sum of all possible combinations of $i$ roots multiplied together, or the $i$th elementary symmetric sum of set $r$. We also have to multiply by the negative sign, resulting in $(-1)^i$

We can refactor to state:

$$
\sum _{sym}^i r = (-1)^i \frac {c_{n-i}} {c_n}
$$