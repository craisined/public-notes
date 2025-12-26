#Calculus #Math
# Background - Analytic Continuation
$$
\int _0^\infty e^{-st} dt = \frac 1 {s}
$$
is used as an analytic continuation of the function. For the Laplace Transform to work, most of the integrals used must be extended to analytic continuations.
# Definition - Laplace Transform
$$
F(s) = \int _0^\infty f(x) e^{-st} dt
$$
# Intuition - The $e^{sx}$ Finding Machine
Take $f(x)$ as $\sum c_n e^{at}$. Plugging into the Laplace Transform:
$$
F(s) = \int _0^\infty \sum c_ne^{(a - s)t} dt
$$
$$
= \sum c_n \int _0^\infty e^{-(s - a)t} dt
$$
$$
= \sum \frac {c_n} {s - a}
$$
Therefore the Laplace Transform of a function reveals both $c_n$ and $s$ in the sum based upon the parts that make up the transform: poles reveal all $s$ values, while the "magnitude" of each pole reveals the magnitude of each $e^{sx}$ term.