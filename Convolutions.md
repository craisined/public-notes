#Math #Probability

# Discrete Case

Let’s create a function expressing the probability two functions results have a sum of $s$.

$$
\sum _{x = -\infty}^{\infty} f(x)g(s-x)
$$

Let's unpack this formula. The inside of the sum finds the probability of a single case where $f$ and $g$ adds to $s$. By using a summation, we can run through every possible case that this happens.

This operation is called a discrete convolution. Convolutions are notated as

$$
[f * g](s)
$$

# Continuous Case

Extending the previous equation over to a continuous function, we can attain a definition like this:

$$
[f * g](s) = \int _{-\infty}^{\infty} f(x)g(s-x) dx
$$

Naturally, we'd expect this to be a probably density function of $f + g$. This is from the same effect as the discrete convolution, except we talk about this for an infinitely small point and probability densities.

# Summary

Convolutions return the probability or probability density of adding two functions together (this depends on the type of function you use).

They are defined by:

Discrete:

$$
[f * g](s) = \sum _{x = -\infty}^{\infty} f(x)g(s-x)
$$

Continuous:

$$
[f * g](s) = \int _{-\infty}^{\infty} f(x)g(s-x) dx
$$