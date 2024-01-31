---
title: Transmon Hamiltonian
date: 2023-09-04
authors:
  - name: Akinori Machino
---

# トランズモンのハミルトニアン

超伝導電荷量子ビットのハミルトニアンは、生成消滅演算子 $b, b^\dagger$ を用いて、

$$
\begin{aligned}
H & =\sqrt{2 E_C E_J}\left(\frac{b-b^\dagger}{\sqrt{2} i}\right)^2
-E_J \cos \left[\left(\frac{8 E_C}{E_J}\right)^{\frac{1}{4}}\left(\frac{b+b^\dagger}{\sqrt{2}}\right)\right] \\
\end{aligned}
$$

と記述できることが知られている[^1]。

[^1]: 要補足

ここでは、このハミルトニアンは所与のものとして、

$$
\frac{E_C}{E_J} \ll 1
$$

を満たすように設計された素子であるトランズモン (transmon) に対して、近似的なハミルトニアンを導出しよう。

$\lambda = \frac{E_C}{E_J}$ とおき、 $\cos$ 部分の項をテイラー展開すると、

$$
\begin{aligned}
H & =\sqrt{2 E_C E_J}\left(\frac{ b - b^\dagger}{\sqrt{2} i}\right)^2
-E_J \cos \left[\left(\frac{8 E_C}{E_J}\right)^{\frac{1}{4}}\left(\frac{ b + b^\dagger}{\sqrt{2}}\right)\right] \\
&= -E_J \left\{
\left(\frac{\lambda}{2}\right)^{\frac{1}{2}}\left( b - b^\dagger\right)^2
+ \cos \left[\left(2 \lambda\right)^{\frac{1}{4}}\left( b + b^\dagger\right)\right]
\right\} \\
&= -E_J \left\{
\left(\frac{\lambda}{2}\right)^{\frac{1}{2}}\left( b - b^\dagger\right)^2
+ 1 - \frac{\left(2\lambda \right)^{\frac{2}{4}}}{2!}\left( b + b^\dagger\right)^2 + \frac{\left(2\lambda \right)^{\frac{4}{4}}}{4!}\left( b + b^\dagger\right)^4 - \frac{\left(2\lambda \right)^{\frac{6}{4}}}{6!}\left( b + b^\dagger\right)^6 + \cdots
\right\} \\
&= -E_J \left\{
1 + \sqrt\frac{\lambda}{2}\left( b - b^\dagger\right)^2
- \sqrt\frac{\lambda}{2}\left( b + b^\dagger\right)^2
+ \frac{\lambda}{12}\left( b + b^\dagger\right)^4
+ \frac{\sqrt{2}\lambda^{\frac{3}{2}}}{360}\left( b + b^\dagger\right)^6
+ O\left(\lambda^{2}\right)
\right\} \\
\end{aligned}
$$

まず、2 次の $\cos$ まで計算してみよう。

$$
\begin{aligned}
(b + b^\dagger)^2 &= b^2 + b b^\dagger + b^\dagger b + (b^\dagger)^2 \\
&= b^2 + \left(b^\dagger b + 1 \right) + b b^\dagger + (b^\dagger)^2 \\
&= b^2 + 2 b^\dagger b + (b^\dagger)^2 + 1 \\
(b - b^\dagger)^2 &= b^2 - b b^\dagger - b^\dagger b + (b^\dagger)^2 \\
&= b^2 - \left(b^\dagger b + 1 \right) - b b^\dagger + (b^\dagger)^2 \\
&= b^2 - 2 b^\dagger b + (b^\dagger)^2 - 1 \\
\end{aligned}
$$

$$
\begin{aligned}
(b + b^\dagger)^2 -
(b - b^\dagger)^2
&=
4 b^\dagger b + 2 \\
&= 4 \left( b^\dagger b + \frac{1}{2} \right) \\
\end{aligned}
$$

であることに注意すれば、

$$
\begin{aligned}
H^{(2)} &= -E_J + \sqrt{8\lambda}\left( b^\dagger b + \frac{1}{2}\right) \\
&= -E_J + \sqrt{8 E_C E_J}\left( b^\dagger b + \frac{1}{2}\right) \\
\end{aligned}
$$

となる。この $H^{(2)}$ は、調和振動子のハミルトニアンと同等であるため、2 次までの展開ではトランズモンの非調和性を表せていない。

次に、4 次の項まで考慮した

$$
\begin{aligned}
H^{(4)} &= H^{(2)} - \frac{E_C}{12} \left( b + b^\dagger \right)^4
\end{aligned}
$$

を計算してみよう。

$b, b^\dagger$ は可換でないため、 $(b + b^\dagger)^4$ を展開すると $2^4 = 16$ 項が現れるが、そのうち $b$ と $b^\dagger$ が同数現れる項のみを考慮することにする[^2]。

[^2]: 要補足

$b$ と $b^\dagger$ が同数は現れる項は $_4 C_2 = 6$ つある：

$$
\begin{aligned}
b^\dagger b^\dagger b b \\
b^\dagger b b^\dagger b \\
b^\dagger b b b^\dagger \\
b b^\dagger b^\dagger b \\
b b^\dagger b b^\dagger \\
b b b^\dagger b^\dagger
\end{aligned}
$$

交換関係 $[b, b^\dagger] = 1$ を用いて、これらをすべて $b^\dagger b^\dagger b b$ の形に書き換えると、

$$
\begin{aligned}
b^\dagger b^\dagger b b
&= b^\dagger b^\dagger b b \\
b^\dagger b b^\dagger b
&= b^\dagger b^\dagger b b + b^\dagger b \\
b^\dagger b b b^\dagger
&= b^\dagger b^\dagger b b + 2 b^\dagger b \\
b b^\dagger b^\dagger b
&= b^\dagger b^\dagger b b + 2 b^\dagger b \\
b b^\dagger b b^\dagger
&= b^\dagger b^\dagger b b + 3 b^\dagger b + 1 \\
b b b^\dagger b^\dagger
&= b^\dagger b^\dagger b b + 4 b^\dagger b + 2
\end{aligned}
$$

であるから、

$$
\begin{aligned}
H^{(4)} &= H^{(2)} - \frac{E_C}{12} \left( b + b^\dagger \right)^4 \\
&\sim -E_J + \sqrt{8 E_C E_J}\left( b^\dagger b + \frac{1}{2}\right) - \frac{E_C}{12} \left(
6 b^\dagger b^\dagger b b + 12 b^\dagger b + 3 \right) \\
&= - E_J - \frac{E_C}{4} + \left( \sqrt{8 E_C E_J} - E_C \right) b^\dagger b
- \frac{E_C}{2} b^\dagger b^\dagger b b
\end{aligned}
$$

となる。

$$
\begin{aligned}
\omega_0 &= \sqrt{8 E_C E_J} - E_C \\
\alpha &= - E_C
\end{aligned}
$$

として、原点を 0 にすれば、

$$
\begin{aligned}
H &= \omega_0 b^\dagger b + \frac{\alpha}{2}   b^\dagger b^\dagger b b \\
&= \omega_0 b^\dagger b + \frac{\alpha}{2}  (b^\dagger)^2 b^2
\end{aligned}
$$

と表せる。これが一般的に用いられるトランズモンのハミルトニアンである[^3] 。

[^3]: ちなみに 4 次までであると、$\lambda = \frac{E_C}{E_J} = 0.01$ の値でハミルトニアンは $O(\lambda^{\frac{3}{2}}) \sim 0.001$ くらいのズレが生まれるので、あまりよい近似ではないように思えるがどうなのだろう。

$\cos$ を 6 次まで展開する場合、同様にして

$$
\begin{aligned}
H^{(6)} &= H^{(4)} - \frac{E_C}{360} \left( b + b^\dagger \right)^6 \\
&\sim A b^\dagger b + B (b^\dagger)^2 b^2 + C (b^\dagger)^3 b^3
\end{aligned}
$$

の形で表せるであろう。

## トランズモンのエネルギー準位

$$
\begin{aligned}
H &= \omega_0 b^\dagger b + \frac{\alpha}{2}   (b^\dagger)^2 b^2
\end{aligned}
$$

で表される、相互作用のないトランズモンのエネルギー準位 $E_n$ は、

$$
\begin{aligned}
H &= \omega_0 b^\dagger b + \frac{\alpha}{2}   (b^\dagger)^2 b^2 \\
&= \omega_0 b^\dagger b + \frac{\alpha}{2}  (b^\dagger b)^2 - \frac{\alpha}{2} (b^\dagger b) \\
&= \left( \omega_0 - \frac{\alpha}{2} \right) b^\dagger b + \frac{\alpha}{2} (b^\dagger b)^2
\end{aligned}
$$

より、

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

| $n$      | $E_n$                                                                 | $\omega_n$           |
| -------- | --------------------------------------------------------------------- | -------------------- |
| $0$      | $0$                                                                   | $\omega_0$           |
| $1$      | $\omega_0$                                                            | $\omega_0 + \alpha$  |
| $2$      | $2\omega_0 + \alpha$                                                  | $\omega_0 + 2\alpha$ |
| $3$      | $3\omega_0 + 3 \alpha$                                                | $\omega_0 + 3\alpha$ |
| $4$      | $4\omega_0 + 6 \alpha$                                                | $\omega_0 + 4\alpha$ |
| $\vdots$ | $\vdots$                                                              | $\vdots$             |
| $n$      | $\left( \omega_0 - \frac{\alpha}{2} \right) n + \frac{\alpha}{2} n^2$ | $\omega_0 + n\alpha$ |

トランズモンでは $\alpha < 0$ であるため、$n$ の増加に従って、エネルギー準位差 $\omega_n$ は $|\alpha|$ ずつ小さくなる。
