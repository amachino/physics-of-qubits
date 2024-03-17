---
title: Transmon Control
date: 2024-02-17
authors:
  - name: Akinori Machino
---

# パルスによるトランズモンの制御

単一のトランズモンの量子状態を、マイクロ波パルスによって制御することを考えよう。

トランズモンの自由ハミルトニアン $H_0$ を

$$
\begin{aligned}
H_0 &= \omega b^\dagger b + \frac{\alpha}{2} b^{\dagger 2} b^2 
\\
&= \omega b^\dagger b + \frac{\alpha}{2}  (b^\dagger b)^2 - \frac{\alpha}{2} (b^\dagger b) \\
&= \left( \omega - \frac{\alpha}{2} \right) b^\dagger b + \frac{\alpha}{2} (b^\dagger b)^2
\end{aligned}
$$

とし、駆動パルスのハミルトニアン $V(t)$ を

$$
\begin{aligned}
V(t) &=  \frac{1}{2} \left\{ \Omega(t) e^{-i \omega_d t} b^\dagger + \Omega^*(t) e^{i \omega_d t} b \right\}
\end{aligned}
$$

とすれば、全体のハミルトニアンは

$$
\begin{aligned}
H &= H_0 + V(t)
\\
&= \left( \omega - \frac{\alpha}{2} \right) b^\dagger b + \frac{\alpha}{2} (b^\dagger b)^2 + \frac{1}{2} \left\{ \Omega(t) e^{-i \omega_d t} b^\dagger + \Omega^*(t) e^{i \omega_d t} b \right\}
\end{aligned}
$$

と表せる。

ここで、$b^\dagger, b$ は量子ビットの生成消滅演算子、 $\omega$ はトランズモン $\ket{g}$, $\ket{e}$ 間の共鳴周波数、$\alpha$ は非調和性、$\omega_d$ は駆動パルスの搬送周波数、$\Omega(t) = I(t) + i Q(t)$ はパルス形状を表す複素振幅 (envelope) である。

### 行列表示

3次元で行列表示をすると、$b, b^\dagger$ は

$$
b =
\begin{bmatrix}
0 & 1 & 0 \\
0 & 0 & \sqrt{2} \\
0 & 0 & 0
\end{bmatrix}
$$

$$
b^\dagger =
\begin{bmatrix}
0 & 0 & 0 \\
1 & 0 & 0 \\
0 & \sqrt{2} & 0
\end{bmatrix}
$$

であるから、

$$
b^\dagger b =
\begin{bmatrix}
0 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 2
\end{bmatrix}
$$

$$
(b^\dagger b)^2 =
\begin{bmatrix}
0 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 4
\end{bmatrix}
$$

$$
b^{\dagger 2} b^2 =
\begin{bmatrix}
0 & 0 & 0 \\
0 & 0 & 0 \\
0 & 0 & 2
\end{bmatrix}
$$


$$
H_0 = 
\begin{bmatrix}
0 & 0 & 0 \\
0 & \omega & 0 \\
0 & 0 & 2 \omega + \alpha
\end{bmatrix}
$$

$$
V(t) = \frac{1}{2}
\begin{bmatrix}
0 & \Omega^*(t) e^{i \omega_d t} & 0 \\
\Omega(t) e^{-i \omega_d t} & 0 & \sqrt{2} \Omega^*(t) e^{i \omega_d t} \\
0 & \sqrt{2} \Omega(t) e^{-i \omega_d t} & 0
\end{bmatrix}
$$

$$
H =
\begin{bmatrix}
0 & \frac{1}{2} \Omega^*(t) e^{i \omega_d t} & 0 \\
\frac{1}{2} \Omega(t) e^{-i \omega_d t} & \omega & \frac{\sqrt{2}}{2} \Omega^*(t) e^{i \omega_d t} \\
0 & \frac{\sqrt{2}}{2} \Omega(t) e^{-i \omega_d t} & 2 \omega + \alpha
\end{bmatrix}
$$

## $\omega_d = \omega$ の場合

まず、駆動パルスの搬送周波数が共鳴周波数 $\omega_d = \omega$ と等しい場合を考えよう。

このとき、 $\omega_d$ の回転座標系に移行し、回転波近似 (Rotating Wave Approximation, RWA) を適用すると、ハミルトニアン $H_{\mathrm{ge}}$ は、 $H_0$ と $b^\dagger b$ が交換することを用いて、

$$
\begin{aligned}
H_{\mathrm{ge}} &= U^\dagger H U -i U^\dagger \dot{U}
\\
&= e^{i \omega b^\dagger b t} H e^{-i \omega b^\dagger b t} - \omega b^\dagger b
\\
&= \frac{\alpha}{2} b^{\dagger 2} b^2 + \frac{1}{2} \left\{ \Omega(t) b^\dagger + \Omega^*(t) b \right\}
\end{aligned}
$$

となる。

行列表示すれば、

$$
H_{\mathrm{ge}} =
\begin{bmatrix}
0 &  \frac{1}{2} \Omega^*(t) & 0 \\
 \frac{1}{2} \Omega(t) & 0 &  \frac{\sqrt{2}}{2} \Omega^*(t) \\
0 & \frac{\sqrt{2}}{2}\Omega(t) & \alpha
\end{bmatrix}
$$



## $\omega_d = \omega + \alpha$ の場合

次に、駆動パルスの搬送周波数が $\omega_d = \omega + \alpha$ となる場合を考えよう。これは、トランズモンの $\ket{e}$, $\ket{f}$ 間の共鳴周波数に等しい場合である。

このとき、 $\omega_d$ の回転座標系に移行し、回転波近似 (Rotating Wave Approximation, RWA) を適用すると、ハミルトニアン $H_{\mathrm{ef}}$ は

$$
\begin{aligned}
H_{\mathrm{ef}} &= U^\dagger H U -i U^\dagger \dot{U}
\\
&= e^{i (\omega + \alpha) b^\dagger b t} H e^{-i (\omega + \alpha) b^\dagger b t} - (\omega + \alpha) b^\dagger b
\\
&= - \alpha b^\dagger b + \frac{\alpha}{2} b^{\dagger 2} b^2 + \frac{1}{2} \left\{ \Omega(t) b^\dagger + \Omega^*(t) b \right\}
\end{aligned}
$$

となる。

行列表示すれば、

$$
H_{\mathrm{ef}} =
\begin{bmatrix}
0 &  \frac{1}{2} \Omega^*(t) & 0 \\
 \frac{1}{2} \Omega(t) & -\alpha &  \frac{\sqrt{2}}{2} \Omega^*(t) \\
0 & \frac{\sqrt{2}}{2}\Omega(t) & -\alpha
\end{bmatrix}
$$

となる。