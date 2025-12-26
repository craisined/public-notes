#Math #Calculus

# Starting the Proof Off

The Taylor Series uses $x^n$ as building blocks for a function:
[[Taylor Series Proof]]


However, we can use $\sin (nx)$ and $\cos(nx)$ as well. This will be our starting point to derive the Fourier Series:

$$
f(x) = a_0\cos (0x) + b_0\sin(0x) + a_1\cos (x) + b_1\sin(x) + a_2\cos (2x) + b_2\sin(2x)... \\
f(x) = a_0 + \sum _{n = 1}^\infty (a_n\sin(nx) + b_n\cos(nx))
$$

This will be the basic equation we will use.

# Finding $a_0$

Let’s integrate the equation on both sides, and bound by $[-\pi, \pi]$:

$$
\int _{-\pi}^\pi f(x) dx = \int _{-\pi}^\pi a_0 dx + \sum _{n = 1}^\infty \int _{-\pi}^\pi a_n\cos(nx) dx + \sum _{n = 1}^\infty \int _{-\pi}^\pi b_n\sin(nx) dx
$$

The first integral evaluates to $2\pi a_0$. Since the third integral is an odd function, it evaluates to $0$. The second integral can be expressed as:

$$
a_n \int _{-\pi}^\pi \cos(nx) dx \\
= \frac {a_n} n (\sin(n\pi) - \sin(-n\pi)) \\
= 0
$$

 So now we have:

$$
2\pi a_0 = \int _{-\pi}^\pi f(x) dx \\
a_0 = \frac 1 {2\pi} \int _{-\pi}^\pi f(x) dx
$$

# Finding $a_n$

Let’s multiply the entire equation by $\cos(mx)$, where $m \in \mathbb{Z}^+$ ($m$ is a positive integer):

$$
f(x)\cos(mx) = a_0\cos(mx) + \sum _{n = 1}^\infty a_n\cos(nx)\cos(mx) + b_n\sin(nx)\cos(mx)
$$

Now integrate on both sides, and bound by $[-\pi, \pi]$:

$$
\int _{-\pi}^\pi f(x)\cos(mx) dx = \int _{-\pi}^\pi a_0\cos(mx) dx + \sum _{n = 1}^\infty \int _{-\pi}^\pi a_n\cos(nx)\cos(mx) dx + \sum _{n = 1}^\infty \int _{-\pi}^\pi b_n\sin(nx)\cos(mx) dx
$$

We have three integrals on the right hand side to evaluate:

## First Integral

$$
\int _{-\pi}^\pi a_0 \cos(mx) dx \\
= \frac{a_0} m \sin(m\pi)- \frac{a_0} m \sin(-m\pi)
$$

Since $m\pi$ is always a multiple of $\pi$:

$$
=0
$$

## Second Integral

$$
\int _{-\pi}^\pi a_n\cos(nx)\cos(mx) dx
$$

Using $\cos$ addition formula:

$$
= \frac {a_0} 2 \int _{-\pi}^\pi \cos(nx + mx) + \cos(nx - mx) dx \\
= \frac {a_0} 2 (\int _{-\pi}^\pi \cos(nx + mx) dx + \int _{-\pi}^\pi  \cos(nx - mx) dx) \\
= [\frac {a_0} 2 (\frac {\sin(nx + mx)} {n + m} + \frac {\sin(nx - mx)} {n - m})]_{-\pi}^{\pi} \\
$$

Here you will notice that this integral doesn’t work for $n = m$. We’ll circle back to that later. For now, this is two odd functions being added together. Since the bounds are the negatives of one another:

$$
= 0
$$

Now, circling back to the extra case, where $n = m$:

$$
a_m\int _{-\pi}^\pi \cos^2(nx)dx \\
= a_m\int _{-\pi}^\pi \frac {1 + \cos(2x)} 2 dx \\
= a_m[\frac x 2 + \frac {\sin 2x} 4 ]_{-\pi}^\pi \\
= a_m[(\frac {\pi} 2 + \frac {\sin 2\pi} 4 ) - (\frac {-\pi} 2 + \frac {\sin -2\pi} 4 )] \\
= a_m\pi
$$

So, the second term in the right hand side evaluates to $a_m\pi$.

## Third Integral

$$
\int _{-\pi}^{\pi} \sin(nx)\cos(mx) dx \\
= \frac 1 2 \int _{-\pi}^{\pi} \sin(nx + mx) dx + \frac 1 2 \int _{-\pi}^\pi \sin(nx - mx) dx \\
= [-\frac 1 2(\frac {\cos(nx + mx)} {n + m} + \frac {\cos(nx - mx)} {n - m})]_{-\pi}^\pi \\
$$

Remember that $\cos x = -cos(x + \pi)$:

$$
= 0
$$

## Putting it Together

Now we have:

$$
\int _{-\pi}^\pi f(x)\cos(mx) dx = a_m\pi \\
\frac 1 \pi \int _{-\pi}^\pi f(x)\cos(mx) dx = a_m
$$

Note in this case $m$ and $n$ both represent any positive integer, and are therefore interchangeable:

$$
a_n = \frac 1 \pi \int _{-\pi}^\pi f(x)\cos(nx) dx \\
$$

# Finding $b_n$

Multiply the equation by $\sin mx$, where $m \in \mathbb{Z}^+$,integrate, and bound between $[-\pi, \pi]$:

$$
\int _{-\pi}^\pi f(x)\sin(mx) dx = \int _{-\pi}^\pi a_0\sin(mx) dx + \sum _{n = 1}^\infty \int _{-\pi}^\pi a_n\cos(nx)\sin(mx) dx + \sum _{n = 1}^\infty \int _{-\pi}^\pi b_n\sin(nx)\sin(mx) dx
$$

The first two terms are already covered, so let’s focus on the final term.

## Last Integral

$$
\int _{-\pi}^\pi b_n\sin(nx)\sin(mx) dx \\
= b_n\int _{-\pi}^\pi \cos(nx - mx) - \cos(nx + mx) dx \\
= b_n [\frac {\sin(nx - mx)} {n - m} - \frac {\sin(nx + mx)} {n + m}]_{-\pi}^\pi
$$

Again, there is a special case where $n = m$. Remember $\sin \pi = 0$, so:

$$
= 0
$$

With the special case:

$$
b_m\int _{-\pi}^\pi \sin^2(mx) dx \\
= b_m\int _{-\pi}^\pi \frac {-\cos(2mx) + 1} 2 dx \\
= b_m[\frac 1 2 (x - \frac {\sin(2mx)} {2m})]_{-\pi}^\pi \\
= b_m\pi
$$

## Putting it Together

$$
b_m\pi = \int _{-\pi}^\pi f(x)\sin(mx) dx \\
b_m = \frac 1 \pi \int _{-\pi}^\pi f(x)\sin(mx) dx \\
b_n = \frac 1 \pi \int _{-\pi}^\pi f(x)\sin(nx) dx
$$

# Fourier Series

Using the above, let’s express $f(x)$ as a Fourier Series:

$$
f(x) = \frac 1 {2\pi} \int _{-\pi}^\pi f(x) dx + \sum _{n = 1}^\infty \frac {\cos (nx)} \pi \int _{-\pi}^\pi f(x)\cos(nx) dx + \sum _{n = 1}^\infty \frac {\sin (nx)} \pi \int _{-\pi}^\pi f(x)\sin(nx) dx
$$

Note that this representation only works for when the function repeats from $[0, 2\pi]$. Using a similar proof, we can get:

$$
f(x) = \frac 1 P \int _{-\frac P 2}^{\frac P 2} f(x) dx + \sum _{n = 1}^\infty \frac {2 \cos (\frac {2\pi nx} P)} P \int _{-\frac P 2}^{\frac P 2} f(x)\cos(\frac {2\pi nx} P) dx + \sum _{n = 1}^\infty \frac {2 \sin (\frac {2\pi nx} P)} P \int _{-\frac P 2}^{\frac P 2} f(x)\sin(\frac {2\pi nx} P) dx
$$