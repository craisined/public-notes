#Calculus 
# Problem
$$
\Psi(x) = f(x) + \lambda \int _0^1 (1 + xy)\Psi(y)dy
$$
**A.** Given $f(x) = x$, $\lambda = 1$, find $\Psi$
**B.** Given $f(x) = 0$, find eigenvalues $\lambda$ and corresponding eigenfunctions $\Psi$
# Solutions
## Part A
$$
\Psi(x) = x + \int _0^1 (1 + xy)\Psi(y)dy
$$
Set the kernel as $K(x, y) = 1 + xy$, $C_y = \int _0^1 K(x, y)\Psi(y)dy$:
$$
C_y = \int _0^1 K(x, y)\Psi(y)dy
$$
$$
C_y = \int _0^1 K(x, y)(x + C_y)dy
$$
$$
C_y = (x + C_y) \int _0^1 K(x, y) dy
$$
$$
C_y = (x + C_y)(1 + \frac x 2)
$$
$$
-\frac {C_yx} 2 = x + \frac {x^2} 2
$$
$$
C_y = - 2 - x
$$
Therefore:
$$
\Psi(x) = -2
$$
## Part B
$$
\Psi(x) = \lambda \int _0^1 (1 + xy)\Psi(y)dy
$$
$$
\Psi(x) = \lambda(\int _0^1 \Psi(y) dy + x\int _0^1 y\Psi(y)dy)
$$
Let $C_y = \int _0^1 \Psi (y) dy$, $S_y = \int _0^1 y \Psi(y) dy$:
Equation 1:
$$
C_y = \lambda \int _0^1 (C_y + yS_y) dy
$$
$$
C_y = \lambda (C_y + \frac 1 2 S_y)
$$
$$
C_y = \frac {\lambda S_y} {2(1 - \lambda)}
$$
Equation 2:
$$S_y = \lambda \int _0^1 y(C_y + yS_y) dy$$
$$S_y = \lambda (\frac 1 2 C_y  + \frac 1 3 S_y)$$
$$
S_y = \frac {\frac \lambda 2 C_y} {1 - \frac \lambda 3}
$$
$$S_y = \frac {3\lambda C_y} {2(3 - \lambda)}$$
Substituting:
$$
C_y = \frac {\lambda} {2(1 - \lambda)} \cdot \frac {3\lambda C_y} {6 - 2\lambda}
$$
$$
C_y = \frac {3\lambda^2} {4(1 - \lambda)(3 - \lambda)} C_y
$$
$$
1 = \frac {3\lambda^2} {4(1 - \lambda)(3 - \lambda)}
$$
$$4(1 - \lambda)(3 - \lambda) = 3\lambda^2$$
$$
\lambda^2 - 16\lambda + 12 = 0
$$
$$
\lambda = 8 \pm 2\sqrt{13}
$$
Substitute in for eigenfunctions!
# Notes
- [Reference](https://www.ruf.rice.edu/~baring/phys516/phys516_2021_lec_042921.pdf) used to figure out Fredholm equations and kernel integration
- This was part of a really old final from SJSU! Thank you Mr. A, this was a very cool problem :D