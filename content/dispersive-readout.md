---
title: Dispersive Readout
date: 2025-06-14
authors:
  - name: Akinori Machino
---

# 量子ビットの分散読み出しの有効ハミルトニアン

読み出し共振器 ($\omega_r$) と量子ビット ($\omega_q$) が、結合定数 $g$ で結合する Jaynes-Cummings モデル

$$
\begin{aligned}
H = \omega_r a^\dagger a + \omega_q \sigma_+ \sigma_- + g \left( a^\dagger \sigma_- + a \sigma_+ \right)
\end{aligned}
$$

からスタートし、分散読み出しの有効ハミルトニアン

$$
\begin{aligned}
H' = \left( \omega_r - \chi \sigma_z \right) a^\dagger a + \tilde\omega_q \sigma_+ \sigma_- 
\end{aligned}
$$

を摂動論的に導出しよう。

$\Delta = \omega_q - \omega_r$ とし、分散極限 $|g/\Delta| \ll 1$ を仮定して、Schrieffer-Wolff 変換を適用する。

$$
\begin{aligned}
H_0 &= \omega_r a^\dagger a + \omega_q \sigma_+ \sigma_-
\\
V &= g \left( a^\dagger \sigma_- + a \sigma_+ \right)
\end{aligned}
$$

と分け、

$$
[H_0, S] = -V
$$

を満たす反エルミート演算子 $S$ を求める。

$$
S = \alpha(a^\dagger \sigma_- - a \sigma_+)
$$

の形を仮定し、 $[H_0, S] = -V$ を満たす $\alpha$ を求める。
$$
\begin{aligned}
[H_0, S] &= \alpha \left[ \omega_r a^\dagger a + \omega_q \sigma_+ \sigma_-, a^\dagger \sigma_- - a \sigma_+ \right]
\\
&= \alpha \left(\omega_r \left[ a^\dagger a, a^\dagger \sigma_- - a \sigma_+ \right] +  \omega_q \left[ \sigma_+ \sigma_-, a^\dagger \sigma_- - a \sigma_+ \right] \right)
\end{aligned}
$$

ここで、$\left[ a^\dagger a, a^\dagger \sigma_- - a \sigma_+ \right]$ と $\left[ \sigma_+ \sigma_-, a^\dagger \sigma_- - a \sigma_+ \right]$ を計算する。

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
&= e^{-S} H_0 e^S + e^{-S} V e^S
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
H' \simeq H_0 + \frac{1}{2} \left[ V, S \right]
\end{aligned}
$$

である。


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
&= \frac{g^2}{\Delta} \left(
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

となる。

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

また、 $\sigma_z$ の固有値は $+1$ と $-1$ であるから、分散読み出しの有効ハミルトニアンは、量子ビットが基底状態、励起状態のときに、それぞれ読み出し共振器の周波数が $\omega_r - \chi$、$\omega_r + \chi$ になることを意味する。

また、

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

とも書ける。