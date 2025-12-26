#Math #NT 

For the proof, let p and q be coprime 

# Rearrangement

$$
x=a \: mod \: p\\
x=b \: mod \: q
$$

Subtract a from both equations

$$
x-a=0 \: mod \: p\\
x-a=b-a \: mod \: q
$$

# The Underlying Problem

Let m be an integer from 0 to q-1 (inclusive), and r be an integer from 0 to q-1 (inclusive)

$$
mp=r \: mod \: q
$$

There are q possible values of m, and q possible values of r.

Since p and q are coprime, the remainders cannot repeat until after m > q-1

Therefore, there is a unique value of m to produce any remainder r in the above equation.

# Putting it all Together

If we look at the last equation in *Rearrangement*, we see it matches the equation in *The Underlying Problem*, where b-a corresponds to r, and x-a corresponds to mp.

So, we can see there is one unique solution for x in the interval of 0 to pq-1 (inclusive)

We can extend this by saying there will be a solution pq larger than another solution, making the solutions expressible via mod.

# The Underlying Problem (but rigour)

<aside>

hi LH, this was actually one of the theorems that got me into compo math (Raina can actually vouch). as such the above section is lwk bad, so here is an update since you asked

(oh jeez I did not know how latex worked back then sorry)

</aside>

Again start with

$$
mp \equiv r \mod q
$$

Suppose $m_1$ and $m_2$ are two $m$ that give the same $r$. Then $pm_1 \equiv pm_2 \mod q$. By the cancellation law $m_1 \equiv m_2 \mod q$, since $\gcd(p, q) = 1$.

### Cancellation Law Proof (Brownie Points)

$$
pm_1 - pm_2 = p(m_1 - m_2)
$$

Know $q$ divides $pm_1 - pm_2$ since they are both the same mod $q$, therefore $q$ divides the RHS. By Euclid’s Lemma $q$ must divide $m_1 - m_2$, meaning $m_1 \equiv m_2 \mod q$.

# Final Theorem

Let p and q be coprime. If:

then:

$$
x \: rem \: pq
$$

exists and is unique.

# Notes

$$
x \: = 0 \: mod \: y\\
x \: rem \: y = 0
$$

both mean x is divisible by y.

$$
x=a \: mod \: p\\
x=b \: mod \: q
$$