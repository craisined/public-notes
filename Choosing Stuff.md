#Math #Probability

# Problem

Given $m$ items of one type and $n$ items of another type, what is the probability of choosing $l$ items of type one and $o$ items of type two if you pick $l + o$ items?

# Solution

Total ways to choose the items not considering types:

 

$$
{m + n} \choose {l + o}
$$

Total ways to choose $l$ items of type one: 

$$
m \choose l
$$

Total ways to choose $o$ items of type two: 

$$
n \choose o
$$

Multiply the ways to choose both items to get the number of ways to choose $l$ items of type one and $o$ items of type two, divide by total number of combinations: 

$$
\frac {{m \choose l} {n \choose o}} {{m + n} \choose {l + o}}
$$