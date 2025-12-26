#Math #Trig

# Definition

## Definition in terms of $e$

We define $\cosh$ and $\sinh$ to be the even and odd parts of $e^x$ respectively:

$$
\cosh x = \frac {e^x + e^{-x}} 2 \\
\sinh x = \frac {e^x - e^{-x}} 2
$$

Note this gives us:

$$
\sinh x + \cosh x = e^x
$$

similar to Euler's Formula for circular trig functions.

## Definition in terms of a hyperbola

[https://www.desmos.com/calculator/ixmjpfmukk](https://www.desmos.com/calculator/ixmjpfmukk)

Know that the geometric definition of $\cosh$ is that $B = \cosh 2b$, where $b$ is the blue area. To find $b$, we can use:

$$
b = \frac {B\sqrt{B^2 - 1}} 2 -\int _1^B \sqrt {x^2 - 1} dx \\
= \frac {B\sqrt{B^2 - 1}} 2 - \frac {B\sqrt {B^2 - 1} - \ln(B + \sqrt {B^2 - 1})} 2\\
= \frac {\ln(B + \sqrt {B^2 - 1})} 2
$$

Now let $a = 2b = -\ln(B + \sqrt {B^2 - 1})$. Now we can solve for $B$ in terms of $a$ to define $\cosh$:

$$
a = \ln(B + \sqrt {B^2 - 1}) \\
B = \frac {e^a + e^{-a}} 2 \\
\cosh x = \frac {e^x + e^{-x}} 2
$$

Now using the fact $\cosh$ and $\sinh$ lie on a hyperbola (can be proved algebraically) we get:

$$
\sinh x = \frac {e^x - e^{-x}} 2
$$