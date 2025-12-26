#Math #Calculus

# Theorem

Let $f(x, t)$ be such that both $f(x, t)$ and its partial derivative $f_x (x, t)$ be continuous in $t$ and $x$ in a region of the $xt$-plane, such that $a(x) \leq t \leq b(x)$, $x_0 \leq x \leq x_1$. Also let $a(x)$ and $b(x)$ be continuous and have continuous derivatives for $x_0 \leq x \leq x_1$. Then, for $x_0 \leq x \leq x_1$:

$$
\frac d {dx} (\int _{a(x)}^{b(x)} f(x, t) dt) = f(x, b(x)) \cdot \frac d {dx} b(x) - f(x, a(x)) \cdot \frac d {dx} a(x) + \int _{a(x)}^{b(x)} \frac \partial {\partial x} f(x, t) dt
$$

Notably, this also means:

$$
\frac d {dx} (\int _{c_1}^{c_2} f(x) dx) = \int _{c_1}^{c_2} \frac d {dx} f(x) dx
$$

# Proof

Let $\varphi(x) = \int _a^b f(x, t) dt$ where $a$ and $b$ are functions of $x$i. Define $\Delta a = a(x + \Delta x) - a(x)$ and $\Delta b = b(x + \Delta x) - b(x)$. Then,

$$
\Delta \varphi = \varphi(x + \Delta x)- \varphi(x) \\
= \int _{a + \Delta a}^{b + \Delta b} f(x + \Delta x, t) dt - \int _a^b f(x, t) dt \\ 
$$

Now expand the first integral by integrating over 3 separate ranges:

$$
\int _{a + \Delta a}^a f(x + \Delta x, t) dt + \int _a^b f(x + \Delta x, t) dt + \int _b^{b + \Delta b} f(x + \Delta x, t) dt - \int _a^b f(x, t) dt \\
= -\int _a^{a + \Delta a} f(x + \Delta x, t) dt + \int _a^b [f(x + \Delta x, t) - f(x, t)]dt + \int _b^{b + \Delta b} f(x + \Delta x, t) dt
$$

From mean value theorem we know $\int _a^b f(t) dt = (b - a)f(\xi)$, which applies to the first and last integrals:

$$
\Delta \varphi = -\Delta a f(x + \Delta x, \xi_1) + \int _a^b [f(x + \Delta x, t) - f(x, t)]dt + \Delta b f(x + \Delta x, \xi_2) \\
\frac {\Delta \varphi} {\Delta x} = -\frac {\Delta a} {\Delta x} f(x + \Delta x, \xi_1) + \int _a^b \frac {f(x + \Delta x, t) - f(x, t)} {\Delta x} dt + \frac {\Delta b} {\Delta x} f(x + \Delta x, \xi_2) \\
$$

Now as we set $\Delta x \to 0$, we can express many of the terms as definitions of derivatives (note we pass the limit sign through the integral via bounded convergence theorem). Note now that $\xi_1 \to a$ and $\xi_2 \to b$, which gives us:

$$
\frac d {dx} \int _a^b f(x, t) dt = -\frac {da} {dx} f(x, a) + \int _a^b \frac {\partial} {\partial x} f(x, t) dt + \frac {db} {dx} f(x + \Delta x, b) \\
$$