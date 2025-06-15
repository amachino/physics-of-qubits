---
title: Dispersive Readout
date: 2025-06-14
authors:
  - name: Akinori Machino
---

# 量子ビット分散読み出しのハミルトニアン

読み出し共振器 ($\omega_r$) と量子ビット ($\omega_q$) が、結合定数 $g$ で結合する Jaynes-Cummings モデル

$$
\begin{aligned}
H = \omega_r a^\dagger a + \omega_q \sigma_+ \sigma_- + g \left( a^\dagger \sigma_- + a \sigma_+ \right)
\end{aligned}
$$

からスタートし、分散読み出し (dispersive readout) の有効ハミルトニアン

$$
\begin{aligned}
H' = \left( \omega_r - \chi \sigma_z \right) a^\dagger a + \tilde\omega_q \sigma_+ \sigma_- 
\end{aligned}
$$

を摂動論的に導出しよう。

$\Delta = \omega_q - \omega_r$ とし、分散極限 (dispersive limit) $|\frac{g}{\Delta}| \ll 1$ を仮定して、Schrieffer-Wolff 変換を適用する。

ハミルトニアン $H$ を基底項 $H_0$ と摂動項 $V$

$$
\begin{aligned}
H_0 &= \omega_r a^\dagger a + \omega_q \sigma_+ \sigma_-
\\
V &= g \left( a^\dagger \sigma_- + a \sigma_+ \right)
\end{aligned}
$$

とに分け、

$$
[H_0, S] = -V
$$

を満たす反エルミート演算子 $S$ を求める。

$$
S = \alpha(a^\dagger \sigma_- - a \sigma_+)
$$

の形を仮定し、$\alpha$ を求めよう。
$$
\begin{aligned}
[H_0, S] &= \alpha \left[ \omega_r a^\dagger a + \omega_q \sigma_+ \sigma_-, a^\dagger \sigma_- - a \sigma_+ \right]
\\
&= \alpha \left(\omega_r \left[ a^\dagger a, a^\dagger \sigma_- - a \sigma_+ \right] +  \omega_q \left[ \sigma_+ \sigma_-, a^\dagger \sigma_- - a \sigma_+ \right] \right)
\end{aligned}
$$

$$
\begin{aligned}
\left[ a^\dagger a, a^\dagger \sigma_- - a \sigma_+ \right] &= \left[ a^\dagger a, a^\dagger \sigma_- \right] - \left[ a^\dagger a, a \sigma_+ \right]
\\
&= [a^\dagger a, a^\dagger] \sigma_- - [a^\dagger a, a] \sigma_+
\\
&= a^\dagger \sigma_- + a \sigma_+
\\
\left[ \sigma_+ \sigma_-, a^\dagger \sigma_- - a \sigma_+ \right] &= \left[ \sigma_+ \sigma_-, a^\dagger \sigma_- \right] - \left[ \sigma_+ \sigma_-, a \sigma_+ \right]
\\
&= a^\dagger \left[ \sigma_+ \sigma_-, \sigma_- \right] - a \left[ \sigma_+ \sigma_-, \sigma_+ \right]
\\
&= - a^\dagger \sigma_- \sigma_+ \sigma_- - a \sigma_+ \sigma_- \sigma_+
\\
&= - a^\dagger \sigma_- (1 - \sigma_- \sigma_+) - a \sigma_+ (1 - \sigma_+ \sigma_-)
\\
&= - a^\dagger \sigma_- - a \sigma_+ 
\end{aligned}
$$

したがって、
$$
\begin{aligned}
[H_0, S] &= \alpha \left\{ \omega_r (a^\dagger \sigma_- + a \sigma_+) - \omega_q (a^\dagger \sigma_- + a \sigma_+) \right\}
\\
&= \alpha (\omega_r - \omega_q) (a^\dagger \sigma_- + a \sigma_+)
\end{aligned}
$$

ここで、 $V = g (a^\dagger \sigma_- + a \sigma_+)$ なので、

$$
\begin{aligned}
\alpha (\omega_r - \omega_q) (a^\dagger \sigma_- + a \sigma_+) = -g (a^\dagger \sigma_- + a \sigma_+)
\end{aligned}
$$
したがって、
$$
\begin{aligned}
\alpha = \frac{g}{\Delta} \quad (\Delta = \omega_q - \omega_r)
\end{aligned}
$$
と求まる。この

$$
S = \frac{g}{\Delta} (a^\dagger \sigma_- - a \sigma_+)
$$

を用いて、 $H$ にユニタリ変換 $U = e^S$ を施す。


$$
\begin{aligned}
H' &= U^\dagger H U
\\
&= e^{-S} H e^S
\\
&= H + \left[ H, S \right] + \frac{1}{2} \left[ \left[ H, S \right], S \right] + \cdots
\end{aligned}
$$

$g$ について2次まで展開すると、

$$
\begin{aligned}
H_0 + V + \left[ H_0, S \right] + \left[ V, S \right] + \frac{1}{2} \left[ \left[ H_0, S \right], S \right]
\end{aligned}
$$

であり、今 Schrieffer-Wolff 変換として

$$
\begin{aligned}
\left[ H_0, S \right] = -V
\end{aligned}
$$

となるように $S$ を選んでいるので、

$$
\begin{aligned}
H' ＝ H_0 + \frac{1}{2} \left[ V, S \right]
\end{aligned}
$$

となる。

$$
\begin{aligned}
\frac{1}{2} \left[ V, S \right] &= \frac{g^2}{2\Delta} \left[ a^\dagger \sigma_- + a \sigma_+, a^\dagger \sigma_- - a \sigma_+ \right]
\\
&= -\frac{g^2}{2\Delta} \left(
\left[ a^\dagger \sigma_-, a \sigma_+ \right] - \left[ a \sigma_+, a^\dagger \sigma_- \right]
\right)
\\
&= -\frac{g^2}{\Delta} \left[ a^\dagger \sigma_-, a \sigma_+ \right]
\\
&= -\frac{g^2}{\Delta} \left(
a^\dagger \left[ \sigma_-, a \sigma_+ \right] + \left[ a^\dagger, a \sigma_+ \right] \sigma_-
\right)
\\
&= -\frac{g^2}{\Delta} \left(
a^\dagger a \left[ \sigma_-, \sigma_+ \right] + \left[ a^\dagger, a \right] \sigma_+ \sigma_-
\right)
\\
&= -\frac{g^2}{\Delta} \left(a^\dagger a \sigma_z - \sigma_+ \sigma_-
\right)
\end{aligned}
$$

であるから、 $H'$ は

$$
\begin{aligned}
H' &= H_0 + \frac{1}{2} \left[ V, S \right]
\\
&= \omega_r a^\dagger a + \omega_q \sigma_+ \sigma_- - \frac{g^2}{\Delta} \left(
a^\dagger a \sigma_z - \sigma_+ \sigma_- \right)
\\
&= \omega_r a^\dagger a + \left( \omega_q + \frac{g^2}{\Delta} \right) \sigma_+ \sigma_- - \frac{g^2}{\Delta} a^\dagger a \sigma_z
\end{aligned}
$$

と書ける。

この第三項 $-\frac{g^2}{\Delta} a^\dagger a \sigma_z$ を共振器の周波数に寄与する項とみなすと、分散読み出しの有効ハミルトニアンは次のように整理できる。

$$
\begin{aligned}
H' &= \omega_r a^\dagger a + \left( \omega_q + \frac{g^2}{\Delta} \right) \sigma_+ \sigma_- - \frac{g^2}{\Delta} a^\dagger a \sigma_z
\\
&= \left( \omega_r - \frac{g^2}{\Delta} \sigma_z \right) a^\dagger a + \left( \omega_q + \frac{g^2}{\Delta} \right) \sigma_+ \sigma_-
\\
&= \left( \omega_r - \chi \sigma_z \right) a^\dagger a + \tilde\omega_q \sigma_+ \sigma_-
\end{aligned}
$$

ここで、 $\chi = \frac{g^2}{\Delta}$ とし、 $\tilde\omega_q = \omega_q + \frac{g^2}{\Delta}$ と定義した。

$\sigma_z$ の固有値は $+1$ と $-1$ であるから、分散読み出しの有効ハミルトニアンは、量子ビットが基底状態 $\ket{g}$ 、励起状態 $\ket{e}$ のときに、それぞれ読み出し共振器の周波数が $\omega_r - \chi$、$\omega_r + \chi$ になることを意味する。

通常、 $\Delta = \omega_q - \omega_r < 0$ であるから、分散シフト $\chi = \frac{g^2}{\Delta}$ は負の値である。つまり、量子ビットが励起状態のとき、読み出し共振器の周波数は下がることになる。

また、第三項 $-\frac{g^2}{\Delta} a^\dagger a \sigma_z$ を量子ビットの周波数に寄与する項とみなすと、分散読み出しの有効ハミルトニアンは次のようにも解釈できる。

$$
\begin{aligned}
H' &= \omega_r a^\dagger a + \left( \omega_q + \frac{g^2}{\Delta} \right) \sigma_+ \sigma_- - \frac{g^2}{\Delta} a^\dagger a \sigma_z
\\
&= \omega_r a^\dagger a +  \left( \omega_q + \frac{g^2}{\Delta} \right) \sigma_+ \sigma_- - \frac{g^2}{\Delta} a^\dagger a (1 - 2 \sigma_+ \sigma_-)
\\
&= \left( \omega_r - \frac{g^2}{\Delta} \right) a^\dagger a + \left( \omega_q + \frac{g^2}{\Delta} + \frac{2g^2}{\Delta} a^\dagger a \right) \sigma_+ \sigma_-
\\
&= \tilde\omega_r a^\dagger a + \left( \tilde\omega_q + 2 \chi a^\dagger a \right) \sigma_+ \sigma_-
\end{aligned}
$$

ここで、 $\tilde\omega_r = \omega_r - \frac{g^2}{\Delta}$ とし、 $\tilde\omega_q = \omega_q + \frac{g^2}{\Delta}$ と定義した。

この形では、量子ビットの周波数が共振器内の光子数 $n = a^\dagger a$ に依存することがわかる。つまり、量子ビットの周波数は、共振器内が1つ増加する毎に $2\chi$ だけシフト（$\chi$ が負の値であれば減少）する。