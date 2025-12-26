#Math #Calculus

# Definition

When

$$
\lim _{x \to c} f(x) = L
$$

For $\epsilon > 0$ and $\delta > 0$, there is a value $\delta$ for every value of $\epsilon$ such that

$$
0 < |x - c| < \delta\\
0 < |f(x) - L| < \epsilon\\
$$

# Proving a Limit

Let’s prove:

$$
\lim _{h \to 0} \frac {(x + h)^2 - x^2} h = 2x
$$

Let:

$$
0 < |\frac {(x + h)^2 - x^2} h - 2x| < \epsilon \\
0 < |\frac {(x + h)^2 - x^2} h - 2x| < \epsilon \\0 < |\frac {(x^2 + 2xh + h^2 - x^2)} h - 2x| < \epsilon \\0 < |\frac {2xh + h^2} h - 2x| < \epsilon \\
$$

Remember $\epsilon > 0$:

$$
0 < |2x + h - 2x| < \epsilon \\
0 < |h| < \epsilon
$$

We have to prove for every $\epsilon$:

$$
0 < |h - 0| < \delta \\
0 < |h| < \delta
$$

These two inequalities are the same, so they are easily satisfied just by setting:

$$
\delta = \epsilon
$$

# Graphical Explanation

[https://www.desmos.com/calculator/tucchymbrq](https://www.desmos.com/calculator/tucchymbrq)