#Math #Calculus

# Proof

Let's express a Fourier Series as:

$$
v = \frac {2\pi nx} P \\
f(x) = \sum _{n = 0}^\infty A_n \cos v + B_n \sin v
$$

We can deduce:

$$
f(x) = \sum _{n = 0}^{\infty} \frac {A_n e^{iv} + A_n e^{-iv} - iB_n e^{iv} + iB_n e^{-iv}} 2 \\
= \sum _{n = 0}^{\infty} 0.5(A_n + iB_n)e^{-iv} + 0.5(A_n - iB_n)e^{iv} \\
= \sum _{n = 0}^{\infty} \frac {e^{-iv}} P \int _{-P/2}^{P/2} f(x) (\cos v + i\sin v) dx + \frac {e^{iv}} P \int _{-P/2}^{P/2} f(x) (\cos -v + i\sin -v) dx \\
= \sum _{n = 0}^{\infty} \frac {e^{-iv}} P \int _{-P/2}^{P/2} f(x)e^{iv} dx + \frac {e^{iv}} P \int _{-P/2}^{P/2} f(x)e^{-iv} dx \\
= \sum _{n = -\infty}^{\infty} \frac {e^{iv}} P \int _{-P/2}^{P/2} f(x)e^{-iv} dx
$$

## Definitions

Definitions of $A_n$ and $B_n$:

[[Fourier Series Proof]]