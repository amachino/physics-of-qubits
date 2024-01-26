---
title: Coupled Qubits
date: 2023-09-04
authors:
  - name: Akinori Machino
---

## 2 準位系の場合

$M=N=2$ の場合を考える。このとき、$H_1$ と $H_2$ は

$$
\begin{aligned}
H_1 &= \begin{pmatrix}
E_1^{(0)} & 0 \\
0 & E_1^{(1)}
\end{pmatrix} \\
H_2 &= \begin{pmatrix}
E_2^{(0)} & 0 \\
0 & E_2^{(1)}
\end{pmatrix} \\
\end{aligned}
$$

となる。また、$H_{\mathrm{int}}$ は

$$
\begin{aligned}
H_{\mathrm{int}} &= g
\begin{pmatrix}
0 & 1 \\
0 & 0
\end{pmatrix}
\otimes
\begin{pmatrix}
0 & 0 \\
1 & 0
\end{pmatrix} \\
&+ g
\begin{pmatrix}
0 & 0 \\
1 & 0
\end{pmatrix}
\otimes
\begin{pmatrix}
0 & 1 \\
0 & 0
\end{pmatrix} \\
&=
\begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & 0 & g & 0 \\
0 & g & 0 & 0 \\
0 & 0 & 0 & 0 \\
\end{pmatrix}
\end{aligned}
$$

となる。したがって、結合ハミルトニアンは

$$
\begin{aligned}
H &= H_1 \otimes I_2
+ I_1 \otimes H_2
+ H_{\mathrm{int}} \\
&= \begin{pmatrix}
E_1^{(0)} & 0 & 0 & 0 \\
0 & E_1^{(0)} & 0 & 0 \\
0 & 0 & E_1^{(1)} & 0 \\
0 & 0 & 0 & E_1^{(1)} \\
\end{pmatrix}
+ \begin{pmatrix}
E_2^{(0)} & 0 & 0 & 0 \\
0 & E_2^{(1)} & 0 & 0 \\
0 & 0 & E_2^{(0)} & 0 \\
0 & 0 & 0 & E_2^{(1)} \\
\end{pmatrix}
+
\begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & 0 & g & 0 \\
0 & g & 0 & 0 \\
0 & 0 & 0 & 0 \\
\end{pmatrix} \\
&= \begin{pmatrix}
E_1^{(0)} + E_2^{(0)} & 0 & 0 & 0 \\
0 & E_1^{(0)} + E_2^{(1)} & g & 0 \\
0 & g & E_1^{(1)} + E_2^{(0)} & 0 \\
0 & 0 & 0 & E_1^{(1)} + E_2^{(1)} \\
\end{pmatrix}
\end{aligned}
$$

となる。

式を簡潔にするために、原点を $E_1^{(0)} + E_2^{(0)}$ に移動しよう。すなわち、

$$
H - (E_1^{(0)} + E_2^{(0)}) I
$$

を $H$ と書き直す。更に、

$$
\begin{aligned}
\omega_1 &= E_1^{(1)} - E_1^{(0)} \\
\omega_2 &= E_2^{(1)} - E_2^{(0)}
\end{aligned}
$$

とおけば、

$$
H = \begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & \omega_2 & g & 0 \\
0 & g & \omega_1 & 0 \\
0 & 0 & 0 & \omega_1 + \omega_2 \\
\end{pmatrix}
$$

と表せる。

これを対角化すると、固有値は

$$
\begin{aligned}
\lambda_1 &= 0 \\
\lambda_2 &= \frac{\omega_1 + \omega_2}{2} - \sqrt{\frac{(\omega_1 - \omega_2)^2}{4} + g^2} \\
\lambda_3 &= \frac{\omega_1 + \omega_2}{2} + \sqrt{\frac{(\omega_1 - \omega_2)^2}{4} + g^2} \\
\lambda_4 &= \omega_1 + \omega_2 \\
\end{aligned}
$$

となる。

$ \Delta = \omega_1 - \omega_2 > 0 $ とすると、

$$
\begin{aligned}
\lambda_2 &= \frac{\omega_1 + \omega_2}{2} - \sqrt{\frac{(\omega_1 - \omega_2)^2}{4} + g^2} \\
&= \frac{\omega_1 + \omega_2}{2} - \frac{\omega_1 - \omega_2}{2} \left(1 + \frac{4g^2}{\Delta^2} \right)^{\frac{1}{2}} \\
&\simeq \frac{\omega_1 + \omega_2}{2} - \frac{\omega_1 - \omega_2}{2} \left(1 + \frac{2g^2}{\Delta^2} \right) \\
&= \omega_2 - \frac{g^2}{\Delta} \\
\end{aligned}
$$

同様に $\lambda_1 \simeq \omega_2 + \frac{g^2}{\Delta}$ であるから、

$$
\begin{aligned}
\lambda_1 &= 0 \\
\lambda_2 &= \omega_2 - \frac{g^2}{\Delta} \\
\lambda_3 &= \omega_1 + \frac{g^2}{\Delta} \\
\lambda_4 &= \omega_1 + \omega_2 \\
\end{aligned}
$$

となる。
