#Math #Probability

# Problem

Why does n choose k, or $\frac{n!}{k!(n-k)!}$ generate the coefficient for $x^ky^{n-k}$ in $(x+y)^n$?

# Explanation

Let’s see what happens when expanding $(x+y)^4$:

$$
(x+y)^4\\
=(x+y)(x+y)(x+y)(x+y)\\
=xxxx+\\
yxxx+xyxx+xxyx+xxxy+\\
yyxx+yxyx+yxxy+xyyx+xyxy+xxyy+\\
xyyy+yxyy+yyxy+yyyx+\\
yyyy
$$

When expanding, notice the number of terms with k of x (and likewise 4-k of y) is the number of combinations of 4 choose k, as you choose k slots to put k x’s in out of 4 slots. Therefore, $(x+y)^n={n \choose 0}x^0y^n+{n \choose 1}x^1y^{n-1}...+{n \choose n-1}x^{n-1}y^1+{n \choose n}x^ny^0$