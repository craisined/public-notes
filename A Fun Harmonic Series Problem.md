#Math #Calculus

# The Problem

If $f(x) = \sum _{k \geq 0} a_k x^k$, and this series converges for $x = x_0$, prove:

$$
\sum _{k \geq 0} a_k x_0^k H_k = \int _0^1 \frac {f(x_0) - f(x_0 y)} {1 - y} dy
$$

where $H_k$ is defined to be the partial sums of the harmonic series ($H_0 = 0$, $H_k = \sum _{i = 1}^k \frac 1 i$ for $k \geq 1$).

(from *The Art of Computer Programming*)

# Solution

Although this problem might seem intimidating with a power series involving the harmonic numbers on the LHS and a summation function inside an integral on the RHS, it is fairly trivial to bring out the summation and express the RHS as a power series:

$$
\int _0^1 \frac {f(x_0) - f(x_0 y)} {1 - y} dy \\
= \int _0^1 \frac {\sum _{k \geq 0} a_k x_0^k - \sum _{k \geq 0} a_k x_0^k y^k} {1 - y} dy \\
= \sum _{k \geq 1} a_k x_0^k \int _0^1  \frac {1 - y^k} {1 - y} dy
$$

The integral factor on the last step is now merely Euler’s integral representation for the harmonic numbers, which is easily proven by the simple fact that $\frac {1 - y^k} {1 - y} = \sum _{i = 0}^{k - 1} y^i$. Therefore:

$$
\sum _{k \geq 0} a_k x_0^k H_k = \int _0^1 \frac {f(x_0) - f(x_0 y)} {1 - y} dy
$$