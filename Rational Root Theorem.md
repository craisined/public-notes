#Math #Algebra

# Proof

Let polynomial

$$
P(x) = \sum _{i = 0}^n c_i x^i
$$

where $c_i \in \mathbb{Z}$ (all values of $c$ are integers).

Now let $P(\frac p q) = 0$, where $p$ and $q$ are coprime integers (let a fraction $\frac p q$ be in simplest form and be a root of $P$).

$$
\sum _{i = 0}^n c_i (\frac p q)^i = 0
$$

Multiplying by $q^n$:

$$
\sum _{i = 0}^n c_i p^n q^{n - i} = 0
$$

Now subtract $c_0 q^n$ from both sides and factor $p$ out to get:

$$
p\sum _{i = 1}^n c_i p^{n - 1} q^{n - i} = -c_0 q^n
$$

Now $p$ must divide $-c_0q^n$. However, we know $p$ cannot divide $q^n$ (since $\frac p q$ is in simplest form / $p$ and $q$ are coprime), so $p$ must divide $c_0$.

Doing the same thing as above but with the $a_n$ term and $q$:

$$
q\sum _{i = 0}^{n - 1} c_i p^n q^{n - i - 1} = -c_n p^n
$$

By the above logic, $q$ must divide $c_n$.

## Conclusion

For all rational roots in simplest form ($\frac p q$ where $p$ and $q$ are coprime integers), $p$ must be a factor of the last coefficient while $q$ must be a factor of the first coefficient.

## Notes

For the curious, coprime integers $p$ and $q$ mean that $\gcd(p, q) = 1$.

If future me or someone else is wondering about the excess definitions, this was made for a friend.