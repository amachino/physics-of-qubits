トランズモンのハミルトニアンは、4 次までの項を取ると、

$$
\begin{aligned}
H &= \omega_0 a^\dagger a + \frac{\alpha}{2}   (a^\dagger)^2 a^2 \\
&= \omega_0 a^\dagger a + \frac{\alpha}{2}  (a^\dagger a)^2 - \frac{\alpha}{2} (a^\dagger a) \\
&= \left( \omega_0 - \frac{\alpha}{2} \right) a^\dagger a + \frac{\alpha}{2} (a^\dagger a)^2
\end{aligned}
$$

で表すことができるため、エネルギー準位 $E_n$ は、

$$
E_n = \left( \omega_0 - \frac{\alpha}{2} \right) n + \frac{\alpha}{2} n^2
$$

となる。

$\ket{n} \to \ket{n+1}$ の間のエネルギー準位差を $\omega_n = E_{n+1} - E_{n}$ とおけば、

$$
\begin{aligned}
\omega_n &= \left( \omega_0 - \frac{\alpha}{2} \right) (n+1) + \frac{\alpha}{2} (n+1)^2 - \left( \omega_0 - \frac{\alpha}{2} \right) n - \frac{\alpha}{2} n^2 \\
&= \left( \omega_0 - \frac{\alpha}{2} \right) + \frac{\alpha}{2} (2n + 1) \\
&= \omega_0 + \alpha n
\end{aligned}
$$

となる。

| $n$      | $n+1$    | $\omega_n$           |
| -------- | -------- | -------------------- |
| $0$      | $1$      | $\omega_0$           |
| $1$      | $2$      | $\omega_0 + \alpha$  |
| $2$      | $3$      | $\omega_0 + 2\alpha$ |
| $\vdots$ | $\vdots$ | $\vdots$             |
| $n$      | $n+1$    | $\omega_0 + n\alpha$ |

トランズモンでは $\alpha < 0$ であるため、$n$ が大きくなるほど、エネルギー準位差 $\omega_n$ は $|\alpha|$ ずつ小さくなることを表している。
