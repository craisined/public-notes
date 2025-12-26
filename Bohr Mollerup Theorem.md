#Math #Calculus

# Intro

The Gamma function $\Gamma(x)$ is a way to extend the factorial function, where $\Gamma(n + 1) = n!$. This gives us two conditions defining $\Gamma (x)$:

$$
\Gamma(1) = 1 \\
\Gamma(x + 1) = x \Gamma (x)
$$

However, by adding a third condition stating $\Gamma (x)$ is logarithimically convex ($\log \circ \space \Gamma$ is convex), we can prove that $\Gamma (x)$ is unique!

# Proof

Let $G$ be a function with the properties above. Since $G(x + 1) = xG(x)$, we can define any $G(x + n)$, where $n \in \mathbb{N}$ as:

$$
G(x + n) = G(x)\prod _{i = 0}^{n - 1}(x + i)
$$

This means that it is sufficient to define $G(x)$ on $x \in (0, 1]$ for a unique $G(x)$.

Let $S(x_1, x_2)$ be defined as $\frac {\log (\Gamma(x_2)) - \log (\Gamma(x_1))} {x_2 - x_1}$. Observe that by log-concavity, for all $0 \lt x \leq 1$ and $n \in \mathbb{N}$:

$$
S(n - 1, n) \leq S(n, n +x) \leq S(n, n + 1) \\
\log (G(n))) - \log (G(n-1)) \leq \frac {\log (G(n + x)) - \log (G(n))} {x} \leq \log (G(n + 1)) - \log (G(n)) \\
\log ((n - 1)!) - \log ((n-2)!) \leq \frac {\log (G(x + n)) - \log ((n - 1)!)} {x} \leq \log (n!) - \log ((n - 1)!) \\
\log(n - 1) \leq \frac {\log (\frac{G(x + n)}{(n - 1)!})} {x} \leq \log(n) \\
\log((n - 1)^x) \leq \log (\frac {G(x + n)}{(n - 1)!})\leq \log(n^x) \\
$$

Raising to the $n$:

$$
(n - 1)^x \leq \frac {G(x + n)}{(n - 1)!}\leq n^x \\
(n - 1)^x(n - 1)! \leq G(x + n)\leq n^x(n - 1)! \\
$$

Using the above work to expand $G(x + n)$:

$$
\frac{(n - 1)^x(n - 1)!} {\prod _{i = 0}^{n - 1}(x + i)} \leq G(x) \leq \frac{n^x(n - 1)!} {\prod _{i = 0}^{n - 1}(x + i)} \\
\frac{(n - 1)^x(n - 1)!} {\prod _{i = 0}^{n - 1}(x + i)} \leq G(x) \leq \frac{n^xn!} {\prod _{i = 0}^n(x + i)}(\frac {n + x} n) \\
$$

Of course, taking the limit as $n$ goes to infinity on both sides by brute force will produce the value of $G(x)$, however I will present a more elegant solution. Notice we can take the inequalities separately, resulting in:

$$
\frac{(n_1 - 1)^x(n_1 - 1)!} {\prod _{i = 0}^{n_1 - 1}(x + i)} \leq G(x)\\
G(x) \leq \frac{n_2^xn_2!} {\prod _{i = 0}^{n_2}(x + i)}(\frac {n_2 + x} {n_2}) \\
$$

This shows that no matter $n_1$ and $n_2$, the equality still holds!

Now we can sub in $n_1 = n + 1$, $n_2 = n$, to get:

$$
\frac{n^xn!} {\prod _{i = 0}^{n}(x + i)} \leq G(x) \leq \frac{n^xn!} {\prod _{i = 0}^{n}(x + i)} (\frac {n + x} n)\\
$$

Taking a limit to infinity on both sides:

$$
\lim _{n \to \infty} \frac{n^xn!} {\prod _{i = 0}^{n}(x + i)} \leq G(x) \leq \lim _{n \to \infty} \frac{n^xn!} {\prod _{i = 0}^{n}(x + i)} (\frac {n + x} n)\\
\lim _{n \to \infty} \frac{n^xn!} {\prod _{i = 0}^{n}(x + i)} \leq G(x) \leq \lim _{n \to \infty} \frac{n^xn!} {\prod _{i = 0}^{n}(x + i)} \\
$$

<aside>
<img src="https://www.notion.so/icons/star_yellow.svg" alt="https://www.notion.so/icons/star_yellow.svg" width="40px" />

Therefore there is only a singular function satisfying $G(x)$, as it is squeezed on $[0, 1)$.

</aside>

# Exercise to the Reader

Prove that the definition:

$$
\Gamma(n) = \int _{0}^{\infty} x^{n - 1} e^{-x} dx 
$$

is valid.