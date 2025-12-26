#Math #NT

# Definition

Euler’s totient function returns the number of integers from $1 \leq k \leq n$ for a positive integer $n$. It is notated as:

$$
\phi(n)
$$

# $\phi(n)$ for Prime Powers

Through prime factorization, for $p^k$, the only positive integers below $p^k$ where $\gcd(p^k, n) > 1$ is where $n = mp$, for $1 \leq m \leq p^{k - 1}$. Therefore:

$$
\phi(p^k) \\ = p^k - p^{k - 1} \\ = p^{k - 1}(p - 1) \\ p^k(1 - \frac 1 p)
$$

# Multiplicative Property of $\phi$

If $m$ and $n$ are coprime:

$$
\phi(m)\phi(n) = \phi(mn)
$$

Proof: Let set $A$ be all numbers coprime to $m$ below $m$, and set $B$ be all numbers coprime to $n$ below $n$.

$$
|A| = \phi(m) \\ |B| = \phi(n)
$$

Let set $D$ be all possible ordered pairs using elements from $A$ and $B$, where the element of $A$ is first. If for each element $(k_1, k_2)$in set $D$ we return a value $\theta$ where:

$$
\theta \equiv k_1 \mod m \\ \theta \equiv k_2 \mod n
$$

CRT ensures $\theta$ is unique to $\mod ab$ and exists. Given the fact $\gcd(x + yz, z) = \gcd(x, z)$, we can say that:

$$
\gcd(\theta, m) = \gcd(k_1, m) = 1 \\ \gcd(\theta, n) = \gcd(k_2, n) = 1 \\ \gcd(\theta, mn) = 1
$$

If we put all $\theta$ in set $C$, we can see that set $C$ has all the elements fitting the above conditions. Looking at the length of $C$:

$$
|C| = \phi(mn) \\
|C| = |A| * |B| = \phi(m)\phi(n) \\
 \phi(mn) = \phi(m)\phi(n)
$$

# Value of $\phi$ for any Number

Let a positive integer $n$ prime factorization be:

$$
n = p_1^{k_1}p_2^{k_2}p_3^{k_3}...p_l^{k_l}
$$

Now using the properties above:

$$
\phi(n) \\
= \prod _{i = 1}^l \phi(p_i^{k_i}) \\
= \prod _{i = 1}^l p_i^{k_i}(1 - \frac 1 {p_i})
$$

Multiplying all $p_i^{k_i}$ gives $n$, so factor that out:

$$
= n \prod _{i = 1}^l (1 - \frac 1 {p_i})
$$

(you can derive most textbook definitions from this formula easily)

Final formula:

$$
\phi(n) = n \prod _{i = 1}^l (1 - \frac 1 {p_i})
$$