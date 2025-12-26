#Math #NT 

# Basel Problem Solution

## Base Sum

$$
\frac {\pi^2} 4 \\
= \frac {\pi^2} 4 \csc^2 (\frac \pi 2) \\
= \frac {\pi^2} {4^2} (\csc^2 (\frac \pi 4) + \csc^2 (\frac \pi 4 + \pi))
$$

Do this operation $a$ times, with the above equation being the second time:

$$
= \frac {\pi^2} {4^{a + 1}}\sum _{n = 1}^{2^{a}} \csc^2(\frac \pi {2^{a+1}} + \frac \pi {2^a}) \\
= \sum _{n = 1}^{2^{a}} \frac {\pi^2} {4^{a + 1}} \csc^2(\frac \pi {2^{a+1}} + \frac \pi {2^a}) \\
= \sum _{n = 1}^{2^{a}} \frac {\pi ^2}{4^{a + 1}} \csc^2(\frac \pi {2^{a+1}} + \frac \pi {2^a}) \\
= \sum _{n = 1}^{2^{a}} (\frac {2^{a + 1}} \pi \sin(\frac \pi {2^{a+1}} + \frac \pi {2^a}))^{-2} \\
$$

As $a$ approaches $\infty$:

$$
= 2\sum _{n=1}^{\infty} (2n - 1)^{-2}
$$

Therefore:

$$
\sum _{n = 1}^{\infty} (2n - 1)^{-2} = \frac {\pi^2} {8}
$$

## Manipulating this Sum

$$
\sum _{n = 1}^{\infty} (2n)^{-2} = \frac 1 4 \sum _{n = 1}^{\infty} n^{-2} \\\sum _{n = 1}^{\infty} (2n - 1)^{-2} = \frac 3 4 \sum _{n = 1}^{\infty} n^{-2} \\\frac {\pi ^2} 8 = \frac 3 4 \sum _{n = 1}^{\infty} n^{-2} \\
\frac {\pi ^2} 6 = \sum _{n = 1}^{\infty} n^{-2} \\
$$

Therefore

$$
\frac {\pi ^2} 6 = \sum _{n = 1}^{\infty} n^{-2} \\
$$