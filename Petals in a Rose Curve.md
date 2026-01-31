#Math #Trig #Algebra 
# Question
Show there are $n$ petals in a rose curve with odd $n$ and $2n$ petals in a rose curve with even $n$.
# Solution
WLOG the rose curve has the form $r = \cos n\theta$.
Then there are 2 cases to get a maximum point on a petal: either $\cos n\theta = 1$ or $\cos( n(\theta + \pi)) = -1$
## Case 1
$$
\cos n\theta = 1
$$
For all integers $i$:
$$
n\theta = 2i\pi
$$
$$
\theta = \frac {2i\pi} n
$$
## Case 2
$$\cos( n(\theta + \pi)) = -1$$
For any arbitrary integer $i$:
$$n(\theta + \pi) = 2i\pi + 1$$
$$\theta = \frac {(2i + 1)\pi - n\pi} n$$
For $\theta \in [0, 2\pi)$ both sequences create 
## Even Case
Factor out $\frac \pi n$ from both sides. Case 1 has $\frac \pi n$ multiplied by an even factor, while case 2 has $\frac \pi n$ multiplied by an odd factor. Therefore the sequences are unique, creating $2n$ unique petals.
## Odd Case
Take case 2:
$$\theta = \frac {(2i + 1)\pi - n\pi} n$$
$$\theta = \frac {2i\pi + (1 - n)\pi} n$$
Since $n$ is odd, $1 - n$ is even, and therefore the numerator is an even factor of $\pi$.
$$\theta = \frac {2i\pi} n$$
Therefore case 2 produces the same $\theta$ as case 1, resulting in $n$ petals.