#Math #Algebra

# Multiplying an Adjacency Matrix by Itself

Consider adjacency matrix $M$ with $n$ nodes. We know that if there is a path between $a$ and $b$, $M_{a, b} = 1$, if not $M_{a, b} = 0$. Now consider all possible nodes $c$ to choose a path $a \to c \to b$. We see that for $c$ to be a possible node $M_{a, c} = 1$ and $M_{c, b} = 1$.

Now observe the definition of multiplication of matrices. We know:

$$
MM_{a, b} = \sum _{c = 1}^n M_{a, c} M_{i, c} 
$$

For each path $c$, each term summed only equals one when $M_{a, c}$ and $M_{c, b}$ are both $1$, or when path $a \to c \to b$ exists. Therefore, the number of paths of length $2$ between $a$ and $b$ is $MM_{a, b}$.

# Taking an Adjacency Matrix to $l$

Now consider a matrix $N$ where there are $N_{a, b}$ paths of length $l$ between $a$ and $b$. Have $M$ be the adjacency matrix for the graph $N$ models. Now say we want all paths of length $l + 1$ that look like $a \to … \to c \to b$. We know the number of paths $a \to … \to c$ of length $l$ is $N_{a, c}$. Similarly, we know there are $M_{c, b}$ paths that satisfy $c \to b$. Therefore, the number of paths that satisfy $a \to … \to c \to b$ is:

$$
N_{a, c}M_{c, b}
$$

Choosing any node $c$ gives the number of paths of length $l + 1$ satisfying $a \to b$:

$$
\sum _{c = 1}^n N_{a, c}M_{c, b} \\
NM_{a, b}
$$

Since $M_{a, b}$ obviously is the amount of paths of length $1$ between $a$ and $b$, by induction, the amount of paths of length $l$ between $a$ and $b$ is:

$$
M^l_{a, b}
$$