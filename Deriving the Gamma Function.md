#Math #Calculus

# Extending the Factorial Function

We know $n!$ has a restricted domain of $n \in \mathbb{N}$, but we want to extend this function to $n \in \mathbb{R}$. To do this, we define two basic properties for the gamma function:

$$
n\Gamma(n) = \Gamma(n + 1) \\
\Gamma(n + 1) = n!, \space n\in \mathbb{N}
$$

# Derivation

We know repeated differentiation can generate a factorial function, so we start by differentiating:

$$
\int _{0}^{\infty} e^{-ax} dx = \frac 1 a
$$

**Lebeniz Integral Rule** allows us to differentiate inside the integral, so by repeated differentiation with respect to $a$ and cancelling out the negative sign we get:

$$
\int _{0}^{\infty} xe^{-ax} dx = \frac 1 {a^2} \\
\int _{0}^{\infty} x^2e^{-ax} dx = \frac 2 {a^3} \\
\int _{0}^{\infty} x^ne^{-ax} dx = \frac {n!} {a^{n + 1}} \\
$$

Plugging $a = 1$ we get:

$$
\Gamma(n) = \int _{0}^{\infty} x^{n - 1} e^{-x} dx 
$$

Plugging the definition into the above properties should affirm that this defines the gamma function.