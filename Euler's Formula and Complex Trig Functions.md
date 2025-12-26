#Math #Trig

# Euler's Formula

Euler's formula states:

$$
e^{i \theta} = i\sin \theta + \cos \theta
$$

## Proof

$$
\frac d {d \theta} \frac {i \sin \theta + \cos \theta} {e^{i \theta}} \\
= e^{-i\theta}(i \sin \theta + \cos \theta) \\
= (e^{-i\theta})(i \sin \theta + \cos \theta)\prime + (e^{-i\theta}) \prime (i \sin \theta + \cos \theta) \\
= (e^{-i\theta})(i \cos \theta - \sin \theta) - i(e^{-i\theta})(i \sin \theta + \cos \theta) \\
= (e^{-i\theta})(i \cos \theta - \sin \theta) - (e^{-i\theta})(i \cos \theta - \sin \theta) \\
= 0
$$

Therefore $\frac {i \sin \theta + \cos \theta} {e^{i \theta}}$ is a constant. Plug in $\theta = 0$, to get $\frac {i \sin \theta + \cos \theta} {e^{i \theta}} = 1$. Multiply both sides by $e^{i\theta}$ to get

$$
e^{i \theta} = i\sin \theta + \cos \theta
$$

## Euler's Identity

Plug $\theta = π$ into Euler's Formula

$$
e^{i \pi} = i\sin \pi + \cos \pi \\
e^{i \pi} = -1
$$

# Trig Functions Redefined

Sine:

$$
e^{i \theta} = i\sin \theta + \cos \theta \\
-e^{-i \theta} = -i\sin -\theta - \cos -\theta \\
-e^{-i \theta} = i\sin \theta - \cos \theta \\
e^{i\theta} - e^{-i\theta} = 2i \sin \theta \\
\sin \theta = \frac {e^{i\theta} - e^{-i\theta}} {2i}
$$

Cosine:

$$
e^{i \theta} = i\sin \theta + \cos \theta \\
e^{-i \theta} = i\sin -\theta + \cos -\theta \\
e^{-i \theta} = -i\sin \theta + \cos \theta \\
e^{i\theta} + e^{-i \theta} = 2\cos \theta \\
\cos \theta = \frac {e^{i\theta} + e^{-i \theta}} 2
$$