---
title: Cross-Resonance Hamiltonian
date: 2024-01-31
authors:
  - name: Akinori Machino
---

# 交差共鳴ゲートのハミルトニアン

共振周波数 $\omega_1, \omega_2$ を持つ2つの量子ビットが結合定数 $g$ で結合している系において、量子ビット 1 を周波数 $\omega_d$ で駆動するときのハミルトニアンを、

$$
\begin{aligned}
H_\mathrm{sys} &= H_0 + H_\mathrm{int}
\\
&= \omega_1 b_1^\dagger b_1 + \omega_2 b_2^\dagger b_2 + g \left( b_1^\dagger b_2 + b_1 b_2^\dagger \right)
\\
H_\mathrm{drive} &= \frac{1}{2} \left( \Omega e^{-i \omega_d t} b_1^\dagger + \Omega^* e^{i \omega_d t} b_1 \right)
\end{aligned}
$$

を用いて、

$$
\begin{aligned}
H &= H_\mathrm{sys} + H_\mathrm{drive}
\end{aligned}
$$

と表すことにする。

$b^\dagger, b$ はそれぞれ、量子ビット（フェルミオン）の生成消滅演算子であり、反交換関係

$$
\begin{aligned}
\left\{ b_i, b_i^\dagger \right\} &= b_i b_i^\dagger + b_i^\dagger b_i = 1
\end{aligned}
$$

を満たす。

ここで、 $H_\mathrm{int}$ に対する Schrieffer-Wolff 変換を適用する。すなわち、

$\Delta = \omega_1 - \omega_2$ とし、反エルミート演算子

$$
\begin{aligned}
S &= - \frac{g}{\Delta} \left( b_1^\dagger b_2 - b_1 b_2^\dagger \right)
\end{aligned}
$$

を用いて、 $H$ にユニタリ変換 $U = e^S$ を施す。

$$
\begin{aligned}
H' &= U^\dagger H U
\\
&= e^{-S} H e^S
\\
&= e^{-S} H_\mathrm{sys} e^S + e^{-S} H_{\mathrm{drive}} e^S
\\
&= H_\mathrm{sys}' + H_\mathrm{drive}'
\end{aligned}
$$

Baker-Campbell-Hausdorff 公式

$$
\begin{aligned}
H' &= e^{-S} H e^S
\\
&= H + \left[ H, S \right] + \frac{1}{2} \left[ \left[ H, S \right], S \right] + \cdots
\end{aligned}
$$

を用いて、$H_\mathrm{sys}'$ と $H_\mathrm{drive}'$ を計算しよう。

$$
\begin{aligned}
H_\mathrm{sys}' &= e^{-S} \left( H_\mathrm{0} + H_\mathrm{int} \right) e^S
\end{aligned}
$$

を $g$ について2次まで展開すると、

$$
\begin{aligned}
H_0 + H_\mathrm{int} + \left[ H_0, S \right] + \left[ H_\mathrm{int}, S \right] + \frac{1}{2} \left[ \left[ H_0, S \right], S \right]
\end{aligned}
$$

であり、今 Schrieffer-Wolff 変換として

$$
\begin{aligned}
H_\mathrm{int} + \left[ H_0, S \right] = 0
\end{aligned}
$$

となるように $S$ を選んでいるので、

$$
\begin{aligned}
H_\mathrm{sys}' = H_0 + \frac{1}{2} \left[ H_\mathrm{int}, S \right]
\end{aligned}
$$

である。

$$
\begin{aligned}
\frac{1}{2} \left[ H_\mathrm{int}, S \right] &= -\frac{g^2}{2\Delta} \left[ b_1^\dagger b_2 + b_1 b_2^\dagger, b_1^\dagger b_2 - b_1 b_2^\dagger \right]
\\
&= \frac{g^2}{2\Delta} \left(
\left[ b_1^\dagger b_2, b_1 b_2^\dagger \right] - \left[ b_1 b_2^\dagger, b_1^\dagger b_2 \right]
\right)
\\
&= \frac{g^2}{\Delta} \left[ b_1^\dagger b_2, b_1 b_2^\dagger \right]
\\
&= \frac{g^2}{ \Delta} \left( b_1^\dagger b_1 b_2 b_2^\dagger - b_1 b_1^\dagger b_2^\dagger b_2 \right)
\\
&= \frac{g^2}{ \Delta} \left( b_1^\dagger b_1 b_2 b_2^\dagger + b_1^\dagger b_1 b_2^\dagger b_2 - b_2^\dagger b_2 \right)
\\
&= \frac{g^2}{ \Delta} \left( b_1^\dagger b_1 - b_2^\dagger b_2 \right)
\end{aligned}
$$

であるから、 $H_\mathrm{sys}'$ は

$$
\begin{aligned}
H_\mathrm{sys}' &= H_0 + \frac{1}{2} \left[ H_\mathrm{int}, S \right]
\\
&= \omega_1 b_1^\dagger b_1 + \omega_2 b_2^\dagger b_2 + \frac{g^2}{ \Delta} \left( b_1^\dagger b_1 - b_2^\dagger b_2 \right)
\\
&= \left( \omega_1 + \frac{g^2}{ \Delta} \right) b_1^\dagger b_1 + \left( \omega_2 - \frac{g^2}{ \Delta} \right) b_2^\dagger b_2
\\
&= \tilde{\omega}_1 b_1^\dagger b_1 + \tilde{\omega}_2 b_2^\dagger b_2
\end{aligned}
$$

となる。

さて、$H_\mathrm{drive}$ については、

$$
\begin{aligned}
\left[b_1, S \right] &= -\frac{g}{\Delta} \left[ b_1, b_1^\dagger b_2 - b_1 b_2^\dagger \right]
\\
&= -\frac{g}{\Delta} \left[ b_1, b_1^\dagger b_2 \right]
\\
&= -\frac{g}{\Delta} \left( b_1 b_1^\dagger - b_1^\dagger b_1 \right) b_2
\\
&= \frac{g}{\Delta} \left( 2 b_1^\dagger b_1 - 1 \right) b_2
\end{aligned}
$$

$$
\begin{aligned}
\left[b_1^\dagger, S \right] &= -\frac{g}{\Delta} \left[ b_1^\dagger, b_1^\dagger b_2 - b_1 b_2^\dagger \right]
\\
&= \frac{g}{\Delta} \left[ b_1^\dagger, b_1 b_2^\dagger \right]
\\
&= \frac{g}{\Delta} \left( b_1^\dagger b_1 - b_1 b_1^\dagger \right) b_2^\dagger
\\
&= \frac{g}{\Delta} \left( 2 b_1^\dagger b_1 - 1 \right) b_2^\dagger
\end{aligned}
$$

$$
\begin{aligned}
\left[H_\mathrm{drive}, S \right] &= \left[ \frac{1}{2} \left\{ \Omega e^{-i \omega_d t} b_1^\dagger + \Omega^* e^{i \omega_d t} b_1 \right\}, S \right]
\\
&= \frac{1}{2} \left\{ \Omega e^{-i \omega_d t} \left[ b_1^\dagger, S \right] + \Omega^* e^{i \omega_d t} \left[ b_1, S \right] \right\}
\\
&= \frac{g}{\Delta} \left( b_1^\dagger b_1 - \frac{1}{2} \right) \left\{ \Omega e^{-i \omega_d t} b_2^\dagger + \Omega^* e^{i \omega_d t}  b_2 \right\}
\end{aligned}
$$

により、1次の摂動項まで計算すると、

$$
\begin{aligned}
H_\mathrm{drive}' &= H_\mathrm{drive} + \left[ H_\mathrm{drive}, S \right]
\\
&= \frac{1}{2} \left\{ \Omega e^{-i \omega_d t} b_1^\dagger + \Omega^* e^{i \omega_d t} b_1 \right\} + \frac{g}{\Delta} \left( b_1^\dagger b_1 - \frac{1}{2} \right) \left\{ \Omega e^{-i \omega_d t} b_2^\dagger + \Omega^* e^{i \omega_d t}  b_2 \right\}
\\
&= \frac{1}{2} \left\{ \Omega e^{-i \omega_d t} b_1^\dagger + \mathrm{H.c.} \right\}
+ \frac{g}{\Delta} \left( b_1^\dagger b_1 - \frac{1}{2} \right) \left\{ \Omega e^{-i \omega_d t} b_2^\dagger + \mathrm{H.c.} \right\}
\end{aligned}
$$

となる。

以上より、

$$
\begin{aligned}
H' &= H_\mathrm{sys}' + H_\mathrm{drive}'
\\
&= \left( \omega_1 + \frac{g^2}{ \Delta} \right) b_1^\dagger b_1 + \left( \omega_2 - \frac{g^2}{ \Delta} \right) b_2^\dagger b_2 + \frac{1}{2} \left\{ \Omega e^{-i \omega_d t} b_1^\dagger + \mathrm{H.c.} \right\}
+ \frac{g}{\Delta} \left( b_1^\dagger b_1 - \frac{1}{2} \right) \left\{ \Omega e^{-i \omega_d t} b_2^\dagger + \mathrm{H.c.} \right\}
\\
&= \tilde{\omega}_1 b_1^\dagger b_1 + \tilde{\omega}_2 b_2^\dagger b_2
+ \frac{1}{2} \left\{ \Omega e^{-i \omega_d t} b_1^\dagger + \mathrm{H.c.} \right\}
+ \frac{g}{\Delta} \left( b_1^\dagger b_1 - \frac{1}{2} \right) \left\{ \Omega e^{-i \omega_d t} b_2^\dagger + \mathrm{H.c.} \right\}
\end{aligned}
$$

の表式を得る。

さらに、ユニタリ変換

$$
\begin{aligned}
U &= e^{-i \left( \tilde{\omega}_1 b_1^\dagger b_1 + \tilde{\omega}_2 b_2^\dagger b_2 \right) t}
\end{aligned}
$$

によって、 $H'$ を量子ビットの回転座標系 $H'_\mathrm{rot}$ に移すと、

$$
\begin{aligned}
H'_\mathrm{rot} &= U^\dagger H' U - i U^\dagger \dot{U}
\\
&= \frac{1}{2} \left\{ \Omega e^{-i \left( \omega_d -\tilde{\omega_1} \right) t} b_1^\dagger + \mathrm{H.c.} \right\}
+ \frac{g}{\Delta} \left( b_1^\dagger b_1 - \frac{1}{2} \right) \left\{ \Omega e^{-i \left( \omega_d -\tilde{\omega_2} \right) t} b_2^\dagger + \mathrm{H.c.} \right\}
\end{aligned}
$$

駆動周波数が $\omega_d = \tilde{\omega_1}$ であれば、回転波近似により

$$
\begin{aligned}
H'_\mathrm{rot} &= \frac{1}{2} \left\{ \Omega b_1^\dagger + \mathrm{H.c.} \right\}
\end{aligned}
$$

となり、量子ビット 1 に対し、周波数 $|\Omega|$ で通常のラビ振動を引き起こす。

これが $\omega_d = \tilde{\omega_2}$ であると、回転波近似により

$$
\begin{aligned}
H'_\mathrm{rot} &= \frac{g}{\Delta} \left( b_1^\dagger b_1 - \frac{1}{2} \right) \left\{ \Omega b_2^\dagger + \mathrm{H.c.} \right\}
\end{aligned}
$$

となり、量子ビット 1 の状態 $\ket{\psi}_1$ に応じて作用が変化するハミルトニアンを得る。

$\ket{\psi}_1 = \ket{0}_1$ のとき、

$$
\begin{aligned}
H'_\mathrm{rot} &= \frac{g}{\Delta} \left( 0 - \frac{1}{2} \right) \left\{ \Omega b_2^\dagger + \mathrm{H.c.} \right\}
\\
&= \frac{1}{2} \left\{ \left( -\frac{g \Omega}{\Delta} \right) b_2^\dagger + \mathrm{H.c.} \right\}
\\
&= \frac{1}{2} \left\{ -\Omega' b_2^\dagger + \mathrm{H.c.} \right\}
\end{aligned}
$$

$\ket{\psi}_1 = \ket{1}_1$ のとき、

$$
\begin{aligned}
H'_\mathrm{rot} &= \frac{g}{\Delta} \left( 1 - \frac{1}{2} \right) \left\{ \Omega b_2^\dagger + \mathrm{H.c.} \right\}
\\
&= \frac{1}{2} \left\{ \left( \frac{g \Omega}{\Delta} \right) b_2^\dagger + \mathrm{H.c.} \right\}
\\
&= \frac{1}{2} \left\{ + \Omega' b_2^\dagger + \mathrm{H.c.} \right\}
\end{aligned}
$$

すなわち、量子ビット 1 の状態が $\ket{0}$ か $\ket{1}$ かに応じて、量子ビット 2 は振動数 $|\Omega'| = |\frac{g \Omega}{\Delta}|$ で逆方向に回転する。これが、交差共鳴ゲートの基本原理である。

また、交差共鳴ゲートで対象量子ビットの $\pi$ 回転を実現するためには、通常の $\pi$ パルスに対して $|\frac{\Delta}{g}|$ 倍のオーダーのエネルギーが必要であることがわかる。