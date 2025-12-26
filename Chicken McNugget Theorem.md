#Math  #NT

# Theorem

Say $m$ and $n$ are two coprime positive integers. The Chicken McNugget Theorem states the highest number that can't be expressed by $am + bn$, $a \in \mathbb{Z}$, $b \in \mathbb{Z}$, and $a, b \geq 0$ is:

$$
mn - m - n
$$

# Proof

Let a purchasable number relative to $m$ and $n$ be able to be represented by

$$
am + bn
$$

Where $a$ and $b$ are two non negative integers

## Lemma 1

Let $A_N \subset \mathbb{Z} \times \mathbb{Z}$ and $A_N$ be all $(x, y)$ such that for $m \in \mathbb{Z}$ and $n \in \mathbb{Z}$, $xm + yn. = N$. For $(x, y) \in A_N$:

$$
A_N = \{(x + kn, y - km): k \in \mathbb{Z}\}
$$

### Proof

By Bezout's Lemma, there exists integers $x\prime$ and $y\prime$ such that $x\prime m + y\prime n = 1$. Then, $Nx\prime m + Ny\prime n = N$. Thus, $A_N$ is nonempty.

Each addition of $kn$ to $x$ adds $kmn$ to $N$, and each subtraction of $km$ from $y$ subtracts $kmn$ from $N$, so all these values are in $A_N$.

To prove these are the only solutions, let $(x_1, y_1) \in A_N$ and $(x_2, y_2) \in A_N$. This means:

$$
mx_1 + ny_1 = mx_2 + ny_2 \\
m(x_1 - x_2) = n(y_2 - y_1) \\
$$

Since $m$ and $n$ are coprime, and $m$ divides $n(y_2 - y_1)$:

$$
y_2 - y_1 \equiv 0 \mod m \\
y_2 \equiv y_1 \mod m
$$

Similarly:

$$
x_2 \equiv x_1 \mod n
$$

Let $k_1, k_2 \in \mathbb{Z}$ such that:

$$
x_2 - x_1 = k_1n \\
y_1 - y_2 = k_2m \\

$$

By multiplying by $m$ and $n$ respectively, we get $k_1 = -k_2$, proving the lemma.

## Lemma 2

 For $N \in \mathbb{Z}$, there is a unique $(a_N, b_N) \in \mathbb{Z} \times \{0, 1, 2… m - 1\}$ such that $a_Nm + b_Nn = N$.

## Proof

There is only one possible $k$ for

$N$ is purchasable if and only if $a_N \geq 0$.

## Lemma 3

$$
0 \leq y - km \leq m - 1
$$

### Proof

If $a_N \geq 0$, we can pick $(a_N, b_N)$ so $N$ is purchasable. If $a_N < 0$, $a_N + kn < 0$ when $k \leq 0$, or $b_N + km < 0$ for $k > 0$.

## Putting it Together

Therefore, the set of non purchasable integers is:

$$
\{xm + yn : x<0, 0 \leq y \leq m -1\}
$$

To maximize this set, we chose $x = -1$ and $y = m - 1$:

$$
-m + (m - 1)n \\
mn - m - n
$$