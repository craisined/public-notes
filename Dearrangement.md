#Math #Probability

# Problem

How many ways are there to arrange a set of $n$ distinct elements such that no element is in it's original position? 

# Solution

The way to arrange the set without consideration for position is:

$$
n!
$$

Now accounting for the values that have one element in it's original position: 

$$
n! - {n\choose 1}(n - 1)!
$$

However, we subtracted arrangements with two elements in their original position twice: 

$$
n! - {n\choose 1}(n - 1)! + {n \choose 2}(n - 2)!
$$

Now, we readded arrangements with three elements in their original position:

$$
n! - {n\choose 1}(n - 1)! + {n \choose 2}(n - 2)! - {n \choose 3}(n - 3)!
$$

This pattern continues by PIE, giving us: 

$$
n! - {n\choose 1}(n - 1)! + {n \choose 2}(n - 2)! - {n \choose 3}(n - 3)! ... + (-1)^n{n \choose n}(n - n)!
$$

Since ${n \choose k}(n - k)! = \frac {n!} {k!}$, we can rewrite as:

$$
\frac {n!} {0!} - \frac {n!} {1!} + \frac {n!} {2!} ... + (-1)^n\frac {n!} {n!} \\
= \sum _{k = 0}^n (-1)^k \frac {n!} {k!} \\
= n! \sum _{k = 0}^n \frac {(-1)^k} {k!}
$$