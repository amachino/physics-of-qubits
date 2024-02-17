---
title: Qubit Control
date: 2024-01-27
authors:
  - name: Akinori Machino
---

# パルスによる量子ビットの制御

単一の量子ビットの量子状態を、マイクロ波パルスによって制御することを考えよう。

量子ビットの自由ハミルトニアンを $H_0$、駆動パルスのハミルトニアンを $V(t)$ とすると、全体のハミルトニアンは

$$
\begin{aligned}
H &= H_0 + V(t)
\\
&= \omega_0 b^\dagger b + \frac{1}{2} \left\{ \Omega(t) e^{-i \omega_d t} b^\dagger + \Omega^*(t) e^{i \omega_d t} b \right\}
\end{aligned}
$$

と表せる。

ここで、$b^\dagger, b$ は量子ビットの生成消滅演算子、 $\omega_0$ は量子ビットの共鳴周波数、$\omega_d$ は駆動パルスの搬送周波数、$\Omega(t) = I(t) + i Q(t)$ はパルス形状を表す複素振幅 (envelope) である。

以下、量子ビットの共鳴周波数 $\omega_0$ とパルスの搬送周波数 $\omega_d$ の差（離調）を $\delta = \omega_d - \omega_0$ と表し、２種類の回転座標系について考えてみよう。

１つ目は、量子ビットの共鳴周波数 $\omega_0$ で回転する座標系、２つ目は、パルスの搬送周波数 $\omega_d$ で回転する座標系である。

## $\omega_0$ で回転する座標系

ユニタリ変換

$$
U = e^{-i H_0 t}
= e^{-i \omega_0 b^\dagger b t}
$$

によって基底変換し、量子ビットの共鳴周波数 $\omega_0$ で回転する座標系でのハミルトニアン $H'$ を考える。

$$
\begin{aligned}
H' &= U^\dagger H U -i U^\dagger \dot{U} \\
&= \omega_0 b^\dagger b + \frac{1}{2} \left\{ \Omega(t) e^{-i (\omega_d - \omega_0) t} b^\dagger + \Omega^*(t) e^{i (\omega_d - \omega_0) t} b \right\} - \omega_0 b^\dagger b \\
&= \frac{1}{2} \left\{ \Omega(t) e^{-i \delta t} b^\dagger + \Omega^*(t) e^{i \delta t} b \right\}
\end{aligned}
$$


## $\omega_d$ で回転する座標系

ユニタリ変換

$$
U = e^{-i \omega_d b^\dagger b t}
$$

によって基底変換し、パルスの搬送周波数 $\omega_d$ で回転する座標系でのハミルトニアン $H''$ を考える。

$$
\begin{aligned}
H'' &= U^\dagger H U -i U^\dagger \dot{U} \\
&= \omega_d b^\dagger b
+ \frac{1}{2} \left\{ \Omega(t) b^\dagger + \Omega^*(t) b \right\}
- \omega_0 b^\dagger b \\
&= \delta b^\dagger b
+ \frac{1}{2} \left\{ \Omega(t) b^\dagger + \Omega^*(t) b \right\} \end{aligned}
$$
