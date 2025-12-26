#Math #NT #Probability

# Problem

Calculate:

$$
P(x, y \in \mathbb{N}: gcd(x, y) = 1)
$$

# Solution

Each number has a $\frac 1 p$ chance to be divisible by prime $p$, so the probability that two numbers do not share prime factor $p$ is

$$
1 - p^{-2}
$$

Therefore, the probability two numbers are coprime is:

$$
\prod _{p \in \mathbb{P}} 1 - p^{-2}
$$

Since $1 - x = (\frac 1 {1 - x})^{-1} = (\sum _{n = 0}^{\infty} x^n)^{-1}$, we can express the above as: 

$$
(\prod _{p \in \mathbb{P}} \sum _{n = 0}^{\infty} p^{-2n})^{-1}
$$

We can choose any $n$ for $p^{2n}$ for each prime $p$, so by the Unique Factorization Theorem (any natural number can be prime factored one and only one way), we get:

$$
(\sum _{n = 0} n^{-2})^{-1} \\
= (\frac {\pi^2} 6)^{-1} \\
= \frac 6 {\pi^2}
$$