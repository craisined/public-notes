#Math #NT

# Theorem

Let $a$ and $m$ be coprime numbers.

$$
a^{\phi(m)} \equiv 1 \mod m
$$

This is a generalization of Fermet's Little Theorem, as $m$ is a prime number in Fermet’s Little Theorem.

# Proof

Let:

$$
A = \{p_1, p_2, p_3,... p_{\phi(m)} \} \mod m \\
B = \{ap_1, ap_2, ap_3,...ap_{\phi(m)}\} \mod m
$$

Where $p_x$ is the $x$th number relatively prime to $m$.

Since $a$ and $p_x$ are coprime to $m$, $ap_x$ is coprime to $m$. Since each $p_x$ is unique, $ap_x$ is unique, which makes set $B$ the same as set $A$.

Since all terms are coprime to $m$:

$$
a^{\phi(m)} \prod _{k = 0}^{\phi(m)} p_k \equiv \prod _{k = 0}^{\phi(m)} p_k \mod m \\
a^{\phi(m)} \equiv 1 \mod m
$$