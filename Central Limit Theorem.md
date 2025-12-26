#Math #Probability

# The Central Limit Theorem

Let us sum $n$ instances from an i.i.d (independent and identical distribution) with defined first and second moments (mean and variance). Center the distribution on $0$ and scale it by its standard deviation. As $n$ goes to infinity, the distribution of that variable goes toward

$$
\frac 1 {\sqrt 2 \pi} e^{- \frac {x^2} 2}
$$

or the standard  normal distribution

## Mathematical Definition

Let Y be the mean of a sequence of n i.i.ds

$$
Y = \frac 1 n \sum _{i=1}^{n} X_i
$$

Let $\mu=E(X_i)$, the expected value of $X$, and $\sigma = \sqrt {Var(X)}$, the standard deviation of $X$

Calculate the expected value of Y, $E(Y)$, and the variance, $Var(Y)$:

$$
E(Y) \\
= E(\frac 1 n \sum _{i=1}^{n} X_i) \\
= \frac 1 n \sum _{i=1}^{n} E(X_i) \\
= \frac 1 n \sum _{i=1}^{n} \mu \\
= \frac {n \mu} {n} \\
= \mu
$$

$$
Var(Y) \\
= Var(\frac 1 n \sum _{i=1}^n X_i) \\
= \frac 1 {n^2} \sum _{i=1}^n Var(X_i) \\
= \frac \sigma n
$$

Let $Y^*$ be centered by $E(Y)$ and scaled by it's standard deviation, $\sqrt {Var(Y)}$

$$
Y^* \\ = \frac {Y - E(Y)} {\sqrt {Var(Y)}} \\ = \frac {Y - \mu} {\sqrt {\frac {\sigma^2} {n}}} \\ = \frac {\sqrt n (Y - \mu)} \sigma \\= \frac {\sqrt n (\frac 1 n \sum _{i=0}^n X_i - \mu)} \sigma \\ = \frac {\frac 1 {\sqrt n} (\sum _{i=0}^n X_i - \mu)} \sigma 
$$

The CLT states

$$
Y^* \overset d \to N(0, 1)
$$

Or $Y^*$ converges in distribution to the standard normal distribution with a mean of 0 and a standard deviation of 1

# Proof

## A Change in Variables

Let $S$ be the sum of our sequence of n i.i.ds

$$
S = \sum _{i=1}^{n} X_i
$$

Let’s calculate $E(S)$ and $Var(S)$

$$
E(S) \\
=E(\sum _{i=1}^n X_i) \\
=\sum _{i=1}^n E(X_i) \\
=\sum _{i=1}^n \mu \\
= n\mu
$$

$$
Var(S) \\
=Var(\sum _{i=1}^n X_i) \\
=\sum _{i=1}^n Var(X_i) \\
=\sum _{i=1}^n \sigma^2 \\
=n\sigma^2
$$

Center $S$ by $E(S)$ and scale it by $\sqrt {Var(S)}$ for $S^*$

$$
S^* \\
= \frac {S - E(S)} {\sqrt {Var(S)}} \\
= \frac {S - n\mu} {\sqrt {n\sigma^2}} \\
= \frac {S - n\mu} {\sqrt {n}\sigma} \\
= \frac {\frac 1 {\sqrt n} (S-n\mu)} { \sigma} \\
= \frac {\frac 1 {\sqrt n} (\sum _{i=0}^n X_i - \mu)} \sigma 
$$

From the above, $Y^*=S^*$. In the proof, we will use $S^*$, as it is easier to manipulate.

## MGFs

An MGF is a function where

$$
M_V(t) = E(e^{tV})
$$

where $V$ is a random variable

(reminder for me to do another notion on this)

### Properties of MGFs

Property 1:

If

$$
C=A+B
$$

Then

$$
M_C(t) \\
= E(e^{tC}) \\
= E(e^{ta + tb}) \\
= E(e^{ta}e^{tb}) \\
= E(e^{ta}) + E(e^{tb}) \\
= M_A(t) + M_B(t)
$$

Property 2:

$$
M_V^{(r)}(0) = E(V^r)
$$

The $r$ derivative of $M_V$ gives the $r$ moment of $V$

Property 3:

Let $A$ be a sequence of random variables with MGFs of $A_1$, $A_2$… $A_n$

If

$$
M_{A_n}(t) \to M_B(t)
$$

Then

$$
A \overset d \to B
$$

### MGF of a Normal Distribution

Let a random variable derived from a standard normal distribution be Z

$$
Z \sim N(0, 1)
$$

$$
M_z(t) \\
= E(e^{xt}) \\
= \int _{-\infty}^{\infty} e^{xt} \frac 1 {\sqrt {2\pi}} e^{-\frac {x^2} 2} dx \\
= \int _{-\infty}^{\infty} \frac 1 {\sqrt {2\pi}} e^{tx-\frac 1 2 x^2} dx \\
= \int _{-\infty}^{\infty} \frac 1 {\sqrt {2\pi}} e^{-\frac 1 2 (x^2 - 2tx )} dx \\
= \int _{-\infty}^{\infty} \frac 1 {\sqrt {2\pi}} e^{-\frac 1 2 (x^2 - 2tx + t ) + \frac 1 2 t^2 } dx \\
= \int _{-\infty}^{\infty} \frac 1 {\sqrt {2\pi}} e^{-\frac 1 2 (x - t)^2 + \frac 1 2 t^2 } dx \\
= e ^ {\frac 1 2 t^2} \int _{-\infty}^{\infty} \frac 1 {\sqrt {2\pi}} e^{-\frac 1 2 (x - t)^2 } dx \\
= e ^ {\frac {t^2} 2} 
$$

## The Argument

To prove the CLT, we need to prove that $S^*$ converges to $N(0, 1)$ as $n \to \infty$. Our approach will be to prove that the MGF of $N(0, 1)$ converges to the distribution of $S^*$ as $n \to \infty$.

$$
S^* \\
= \frac {S - E(S)} {\sqrt {Var(S)}} \\
= \frac {S - n\mu} {\sqrt {n \sigma^2}} \\
= \frac {\sum _{i=1}^{n} X_i - n\mu} {\sqrt n \sigma} \\
= \sum _{i=1}^{n} \frac {X_i - u} {\sqrt n \sigma}
$$

Start manipulating MGF of $S^*$:

$$
M_{S^*}(t) \\
= E(e^{tS^*}) \\
= E(e^{t(\sum _{i=1}^{n} \frac {X_i - u} {\sqrt n \sigma})}) \\
= E(e^{t(\frac {(X-\mu)} {\sqrt n \sigma})})^n \\
= (M_{\frac {(X-\mu)} {\sqrt n \sigma}}(t))^n \\
=(M_{(X - \mu)} (\frac t {\sqrt n \sigma })^n
$$

Expand out Taylor series for $(M_{(x-\mu)}(\frac t {\sqrt n \sigma}))^n$ (note $O(t^3)$ means order $t^3$ and above, and tends to zero as $n$ goes to $\infty$ ):

$$
M_{(X-\mu)}(\frac t {\sqrt n \sigma}) \\
= (M_{(X-\mu)}(0)) + (\frac {M_{(X-\mu)}\prime(0)} {1!})(\frac t {\sqrt n \sigma}) + (\frac {M_{(X-\mu)}\prime\prime(0)} {2!})(\frac t {\sqrt n \sigma})^2 + (\frac {M_{(X-\mu)}\prime\prime\prime(0)} {1!})(\frac t {\sqrt n \sigma})^3 + ...\\
= 1 + (\frac {t} {\sqrt n \sigma})E(X-\mu) + (\frac {t^2} {2 n \sigma^2})E((X-\mu)^2) + (\frac {t^3} {6n ^ {\frac 3 2} \sigma ^ 3})E((X-\mu)^3) + ... \\
= 1 + (\frac t {\sqrt n \sigma})E(X-\mu) + (\frac {t^2}
 {2n \sigma^2})E((X-\mu)^2) + O(t^3) \\
\approx 1 + (\frac t {\sqrt n \sigma})E(X-\mu) + (\frac {t^2}
 {2n \sigma^2})E((X-\mu)^2)
$$

Remember $E(X-\mu) = 0$ and $E((X-\mu)^2) = \sigma^2$

$$
= 1 + (\frac t {\sqrt n \sigma})(0) + (\frac {t^2} {2n \sigma^2})(\sigma ^ 2) \\
= 1 + \frac {t^2} {2n}
$$

Solve for $M_{S^*} (t)$:

$$
M_{S^*}(t) = (1 + \frac {t^2} {2n})^n
$$

Solve $M_{S^*} (t)$ for $\lim _{n \to \infty}$:

$$
\lim _{n \to \infty} M_{S^*}(t) \\
= \lim _{n \to \infty} (1 + \frac {t^2} {2n})^n \\
= \lim _{n \to \infty} (1 + \frac 1 {(\frac {2n} {t^2})})^{\frac {t^2} 2 (\frac {2n} {t^2})} \\
= e^{\frac {t^2} 2}
$$

Since $\lim _{n \to \infty} M_{S^*} (t) \to M_Z(t)$, $\lim _{n \to \infty}S^* \overset d \to N(0, 1)$. Therefore:

$$
Y^* \overset d \to N(0, 1)
$$

proving the Central Limit Theorem

## Summary of the Argument

$$
Y^* = S^* \\
\lim _{n \to \infty} M_{S^*}(t) \to M_Z (t) \\
\lim _{n \to \infty} S^* \to N(0, 1) \\
\lim _{n \to \infty} Y^* \to N(0, 1) \\
$$