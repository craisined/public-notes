#Math #Algebra

# Defining Vectors

Vectors are a list of components. They can be expressed in ij notation by:

$$
\mathbf a = 2i + 3j -4k
$$

or

$$
\vec a = 2i + 3j -4k
$$

You can also express a vector as a matrix:

$$
\vec a = \begin {bmatrix}
2 \\
3 \\
-4 \\
\end {bmatrix} \\
\vec a = \begin {bmatrix} 2 & 3 & -4 \end {bmatrix}
$$

# Adding and Subtracting Vectors

To add vectors, add their corresponding components. For example:

$$
\vec a = 4i + 7j - 9k \\
\vec b = 3i - 5j - 8k \\
\vec a + \vec b = 7i + 2j - 17k
$$

Subtracting vectors works in a similar fashion:

$$
\vec a - \vec b = i + 12j - k
$$

Here are the formulas:

$$
\vec a + \vec b = a_i+b_i \\
\vec a - \vec b = a_i-b_i

$$

Here’s a graph visualizing the addition and subtraction of vectors: [https://www.desmos.com/calculator/gavjpwhnuo](https://www.desmos.com/calculator/gavjpwhnuo)

# Multiplication by Scalar

To multiply a vector by a scalar (regular number), just multiply all the components by that number:

$$
m\vec a = ma_i
$$

# Multiplication by Another Vector: Dot Product

There are two different ways to multiply a vector by another vector. The first way is a dot product. Here is the algebraic definition, where n is the length of the two vectors:

$$
\vec a \cdot \vec b = \sum _{i = 0}^n a_ib_i
$$

With two two dimensional vectors, we can also provide a geometric definition, where $||\vec a||$ is the magnitude of $\vec a$, and $\theta$ is the angle between the vectors:

$$
\vec a \cdot \vec b = ||a|| \: ||b|| \: \cos \theta
$$

As you can see, the dot product returns a single value, or scalar. From the geometric definition, you can see that it describes how much one vector “aligns” to the other.

## Proving that the Definitions are the Same

Let $\vec a$ have a magnitude of $m$ and an angle of $p$, let $\vec b$ have a magnitude of $n$ and an angle of $q$.

$$
\vec a \cdot \vec b \\
= m\cos p \: n \cos q + m\sin p \: n \sin q \\
= mn(\cos p \: cos q + \sin p \: \sin q) \\
= mn\cos(p-q)
$$

Using the algebraic definition, we can get the geometric definition as shown above.

# Cross Product

Let $n$ be a unit vector perpendicular to $\vec a$ and $\vec b$, and $\theta$ be the angle between them. The cross product is:

$$
\vec a \times \vec b = ||\vec a|| \: ||\vec b|| \: \sin \theta \: n
$$