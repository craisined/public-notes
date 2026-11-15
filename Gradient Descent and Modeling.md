# Models
We can view a model as a function $f(x, p_1, p_2, \dots, p_n)$, and we can judge a model's performance via training error $\varepsilon(f, \hat{f})$, where $\hat{f}$ is what we expect the model to output.
## Convexity and Updating
Assume $\varepsilon$ is convex over all $p_1 \dots p_n$. Then, any local decrease in $\varepsilon$ caused by a change in $p_i$ is toward the local minima of $\varepsilon$. This local decrease is in the direction opposite of the derivative, so to update parameter $p_i$:

$$p_{\text{new}} \rightarrow p_{\text{old}} - \alpha \frac{\partial \varepsilon}{\partial p_i}$$

*(where $\alpha$ is a small number, the learning rate)*
## Line of Best Fit
As a simple case, take $f(x, m, b) = mx + b$ and $\varepsilon(f, \hat{f}) = (f - \hat{f})^2$. Then:

$$
\begin{aligned}
m_{\text{new}} &\rightarrow m_{\text{old}} - \alpha \frac{\partial \varepsilon}{\partial m} \\
&= m_{\text{old}} - \alpha \frac{\partial \varepsilon}{\partial f} \frac{\partial f}{\partial m} \\
&= m_{\text{old}} - \alpha \cdot 2(f - \hat{f}) \cdot x
\end{aligned}
$$
$$
\begin{aligned}
b_{\text{new}} &\rightarrow b_{\text{old}} - \alpha \frac{\partial \varepsilon}{\partial b} \\
&= b_{\text{old}} - \alpha \frac{\partial \varepsilon}{\partial f} \cdot \frac{\partial f}{\partial b} \\
&= b_{\text{old}} - \alpha \cdot 2(f - \hat{f})
\end{aligned}
$$
#  More Complicated Models
We can add complexity to a model by expressing it as a composition of simple functions:

$$f = l_1(l_2(l_3(x, p_1, p_2, \dots), q_1, q_2, \dots), r_1, r_2, \dots)$$

Note how this makes updates very convenient:

$$r_1 \rightarrow r_1 - \alpha \frac{\partial \varepsilon}{\partial l_1} \cdot \frac{\partial l_1}{\partial r_1}$$
$$q_1 \rightarrow q_1 - \alpha \frac{\partial \varepsilon}{\partial l_1} \cdot \frac{\partial l_1}{\partial l_2} \cdot \frac{\partial l_2}{\partial q_1}$$

Note that:
1. $\frac{\partial \varepsilon}{\partial l_1}$ and $\frac{\partial l_1}{\partial l_2}$ are easy to compute for easily differentiable $\varepsilon$ and $l$.
2. Different parameter updates share factors, so it is convenient to keep track of $\frac{\partial \varepsilon}{\partial l_1}, \frac{\partial \varepsilon}{\partial l_2}, \dots$ updating parameters going from $l_1$ to $l_2$ to $l_3 \dots$
## Linearity
Note that if $l_1$ and $l_2$ are linear, $l_1 \circ l_2$ is also linear. Therefore, a model composed of linear functions can still only represent a linear relationship.
To resolve this, add non-linearity! Some options are:
* $l = \max(0, x)$ — *(known as ReLU)*
* $l = \frac{1}{1 + e^{-x}}$ — *(known as sigmoid)*
* $l = \arctan(x)$
However, note that these non-linear functions do not guarantee convexity!