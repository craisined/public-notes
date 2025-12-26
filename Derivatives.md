#Calculus #Math
# Intuition & Definition
How can instant rate of change be defined at a point?
Call our function of choice $y$:
Slope of $y$ between $x_1$ and $x_2$:
$$
\frac {y_1 - y_2} {x_1 - x_2}
$$
$$
= \frac {y(x_1) - y(x_2)} {x_1 - x_2}
$$
However, $x_1 \neq x_2$ due to division by $0$.
## Definitions
Avoid division by $0$ via using a limit such that $x_1 \to x_2$:
$$
\frac {dy} {dx} = \lim_{x_1 \to x_2} \frac {y(x_1) - y(x_2)} {x_1 - x_2}
$$
Changing variables:
$$
\frac {dy} {dx} = \lim_{a \to x} \frac {y(a) - y(x)} {a - x}
$$
Define $a = \lim _{\Delta x \to 0}(x + \Delta x)$:
$$
\frac {dy} {dx} = \lim_{\Delta x \to 0} \frac {y(x + \Delta x) - y(x)} {\Delta x}
$$
# Derivative Rules
## Constant Rule
When $y = a$ and $a$ is constant:
$$
\frac {dy} {dx}
$$
$$
= \lim_{\Delta x \to 0} \frac {a - a} {\Delta x}
$$
$$
= \lim_{\Delta x \to 0} \frac {0} {\Delta x}
$$
$$
= 0
$$
## Sum and Difference Rule
$$
\frac {df} {dx} + \frac {dg} {dx}
$$
$$
= \lim_{\Delta x \to 0} \frac {f(x + \Delta x) - f(x)} {\Delta x} + \frac {g(x + \Delta x) - g(x)} {\Delta x}
$$
$$
= \lim_{\Delta x \to 0} \frac {[f(x + \Delta x) + g(x + \Delta x)] - [f(x) + g(x)]}{\Delta x}
$$
$$
= \frac d {dx} (f + g)
$$
## Power Rule

> **Note:** This proof of power rule only extends to $n \in \mathbb{N}$. Power rule can be extended to $n \in \mathbb{Z}$ through the use of the derivative of $\ln$, but this article does not cover such a proof as of now.

$$
\frac {d} {dx} x^n
$$
$$
= \lim_{\Delta x \to 0} \frac {(x + \Delta x)^n - x^n} {\Delta x}
$$

Use a binomial expansion:
$$
= \lim_{\Delta x \to 0} \frac {\sum_{i = 0}^n {n \choose i}x^i{\Delta x}^{n - i} - x^n} {\Delta x}
$$
Take out last term in sum:
$$
= \lim_{\Delta x \to 0} \frac {x^n + \sum_{i = 0}^{n - 1} {n \choose i}x^i{\Delta x}^{n - i} - x^n} {\Delta x}
$$
$$
= \lim_{\Delta x \to 0} \frac {\sum_{i = 0}^{n - 1} {n \choose i}x^i{\Delta x}^{n - i}} {\Delta x}
$$
$$
= \lim_{\Delta x \to 0} \sum_{i = 0}^{n - 1} {n \choose i}x^i{\Delta x}^{n - i - 1}
$$
Bring limit inside sum:
$$
= \sum_{i = 0}^{n - 1} \left[{n \choose i}x^i \lim_{\Delta x \to 0} {\Delta x}^{n - i - 1}\right]
$$
For $i < n - 1$, $\lim {\Delta x \to 0} \Delta x^{n - i - 1} = 0$, so only the case where $i = n - 1$ matters:
$$
= {n \choose {n - 1}} x^{n - 1}
$$
$$
= nx^{n - 1}
$$
>**Therefore:**
>$$ \frac d {dx} x^n = nx^{n - 1} $$
