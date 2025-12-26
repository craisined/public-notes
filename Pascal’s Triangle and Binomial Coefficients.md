#Math #Probability

# Observing Pascal’s Triangle

| n/k | 0 | 1 | 2 | 3 | 4 | 5 |
| --- | --- | --- | --- | --- | --- | --- |
| 0 | 1 |  |  |  |  |  |
| 1 | 1 | 1 |  |  |  |  |
| 2 | 1 | 2 | 1 |  |  |  |
| 3 | 1 | 3 | 3 | 1 |  |  |
| 4 | 1 | 4 | 6 | 4 | 1 |  |
| 5 | 1 | 5 | 10 | 10 | 5 | 1 |

As you can see, Pascal’s Triangle generates:

$$
{n \choose k}
$$

or

$$
\frac{n!}{k!(n-k)!}
$$

But how does this work?

First, we can manually prove the top two rows of Pascal’s Triangle by plugging the values into the binomial coefficient formula.

Afterward, we can use the property of Pascal’s Triangle, taking Pascal’s Triangle as a function P:

$$
P(n + 1, k) = P(n, k) + P(n, k-1)
$$

By proving this property in the binomial coefficient formula, we can deduce that Pascal’s Triangle generates binomial coefficients

# The Proof

$$
\frac{n!}{k!(n-k)!}+\frac{n!}{(k-1)!(n-k+1)!}\\=\frac{n!(n-k+1)}{k!(n-k)!(n-k+1)}+\frac{n!k}{(k-1)!(n-k+1)!k}\\=\frac{n!(n-k+1)}{k!(n-k+1)!}+\frac{n!k}{k!(n-k+1)!}\\=\frac{n!(n+k+1-k)}{k!(n-k+1)!}\\=\frac{n!(n+1)}{k!(n-k+1)!}\\=\frac{(n+1)!}{k!(n-k+1)!}
$$

From this, we have proven that we can generate binomial coefficients using Pascal’s Triangle