#Math #Probability

# The Poisson Distribution

The Poisson Distribution describes a distribution where an event occurs for an interval of time, where there is an a mean number of times the event happens in the same interval of time.

# Binomial Distribution to Poisson Distribution

Binomial Distribution 

$$
\frac {n!} {k!(n-k)!} p^k (1-p)^{n-k}
$$

Binomial Distribution with infinite trials

$$
\lim _{n\to\infty} \frac {n!} {k!(n-k)!} p^k (1-p)^{n-k}
$$

Let a be np, the average success rate in n intervals. This gives us the Poisson Distribution in another form.

$$
\lim _{n\to\infty} \frac {n!} {k!(n-k)!} (\frac {a} {n})^k (1-\frac {a} {n})^{n-k}
$$

$$
\lim _{n\to\infty} \frac {n!} {k!(n-k)!} (\frac {a^k} {n^k}) (1-\frac {a} {n})^n(1-\frac {a} {n})^{-k}
$$

$$
\frac {a^k} {k!} \lim _{n\to\infty} \frac {n!} {n^a(n-k)!} (1-\frac {a} {n})^n(1-\frac {a} {n})^{-k}
$$

Now we have three limits to evaluate

# Evaluating the Limits

## First Limit

$$
\lim _{n \to\infty} \frac {n!} {n^k(n-k)!}
$$

$$
\lim _{n \to\infty} \frac {n(n-1)(n-2)...(n-k)(n-k-1)...(1)} {n^k(n-k)(n-k-1)...(1)}
$$

$$
\lim _{n\to\infty} \frac {n(n-1)...(n-k+1)} {n^k}
$$

$$
\lim _{n\to\infty} (\frac {n} {n})(\frac {n-1} {n})...(\frac {n-k+1} {n})
$$

As n goes to infinity, all the terms tend to 1. Therefore, the limit tends to 1.

## Second Limit

$$
\lim _{n\to\infty} (1-\frac {a} {n})^n
$$

Let u be -n/x (note this tends to negative infinity)

$$
\lim _{n\to\infty}(1+\frac {1} {u})^{-au}
$$

Use definition of e

$$
e^{-a}
$$

## Third Limit

$$
\lim _{n\to\infty}(1-\frac{a} {n})^{-k}
$$

a/n tends to 0

$$
1^k
$$

Therefore this limit tends to 1.

# Putting it together

$$
\frac {e^{-a}a^{k}}{k!}
$$

is the formula for the probability of an event happening k times in an interval of time, where a is the mean number of times of the event happening in the interval of time the event ran in. This is the formula for the Poisson Distribution.