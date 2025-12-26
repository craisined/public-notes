#Math #Calculus 

Represent function using power series:

$$
f(x) = \sum _{n=0}^{\infty} c_n (x-a)^n
$$

Find $c_0$

$$
c_0=f(a)
$$

Take derivative of function

$$
\frac d {dx} f(x) = \sum _{n=0}^\infty c_{n+1} (n+1)(x-a)^n
$$

Find $c_1$

$$
c_1=\frac {d} {dx} f(a)
$$

Take second derivative of function

$$
\frac {d^2} {d^2x} f(x) = \sum _{n=0}^\infty c_{n+2} (n+1)(n+2)(x-a)^n
$$

Find $c_2$

$$
c_2=\frac {\frac {d^2} {d^2x} f(a)} {2}
$$

Take third derivative of function

$$
\frac {d^3} {d^3x} f(x) = \sum _{n=0}^\infty c_{n+3} (n+1)(n+2)(n+3)(x-a)^n
$$

Find $c_3$

$$
c_3=\frac {\frac {d^3} {d^3x} f(a)} {6}
$$

Create general formula for $n$th element of $c$

$$
c_n = \frac {\frac {d^n} {d^nx}f(a)} {n!}
$$

Create general formula for function as polynomial

$$
f(x)=\sum _{n=0}^\infty \frac {\frac {d^n} {d^nx}f(a)} {n!} (x-a)^n
$$