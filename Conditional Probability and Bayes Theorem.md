#Math #Probability

# Conditional Probability

Conditional probability, or the probability of $A$ given $B$ is:

$$
P(A|B)
$$

Let's start with the probability of $P(A \cup B)$. We know that when $P(A | B)$, $B$ is given to be true. Therefore, we must divide the probably of $P(A \cup B)$ by $P(B)$.

$$
P(A | B) = \frac {P(A \cup B)} {P(B)}
$$

This defines $P(A | B)$ for events. When $P(A | B) = P(A)$, $A$ and $B$ are independent.

# Bayes’ Theorem

Let's start with the definitions of conditional probability:

$$
P(A | B) = \frac {P(A \cup B)} {P(B)} \\
P(B | A) = \frac {P(A \cup B)} {P(A)}
$$

Rearrange the second equation to define $P(A \cup B)$:

$$
P(A \cup B) = P(A) P(B | A)
$$

Now substitute that equation into the first equation:

$$
P(A | B) = \frac {P(A) P(B | A)} {P(B)}
$$

The above equation is Bayes' Theorem for events.