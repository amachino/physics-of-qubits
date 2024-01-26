---
title: Coupled Qutrits
date: 2023-09-04
authors:
  - name: Akinori Machino
---

# 3 準位系の場合

$M=N=3$ の場合を考える。このとき、$H_1$ と $H_2$ は

$$
\begin{aligned}
H_1 &= \begin{pmatrix}
E_1^{(0)} & 0 & 0 \\
0 & E_1^{(1)} & 0 \\
0 & 0 & E_1^{(2)}
\end{pmatrix} \\
H_2 &= \begin{pmatrix}
E_2^{(0)} & 0 & 0 \\
0 & E_2^{(1)} & 0 \\
0 & 0 & E_2^{(2)}
\end{pmatrix} \\
\end{aligned}
$$

となる。また、$H_{\mathrm{int}}$ は

$$
\begin{aligned}
H_{\mathrm{int}} &= g
\begin{pmatrix}
0 & 1 & 0 \\
0 & 0 & \sqrt{2} \\
0 & 0 & 0
\end{pmatrix}
\otimes
\begin{pmatrix}
0 & 0 & 0 \\
1 & 0 & 0 \\
0 & \sqrt{2} & 0
\end{pmatrix} \\
&+ g
\begin{pmatrix}
0 & 0 & 0 \\
1 & 0 & 0 \\
0 & \sqrt{2} & 0
\end{pmatrix}
\otimes
\begin{pmatrix}
0 & 1 & 0 \\
0 & 0 & \sqrt{2} \\
0 & 0 & 0
\end{pmatrix} \\
&=
\begin{pmatrix}
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & g & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & \sqrt{2}g & 0 & 0 & 0 & 0 \\
0 & g & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & \sqrt{2}g & 0 & 0 & 0 & \sqrt{2} g & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 2g & 0 \\
0 & 0 & 0 & 0 & \sqrt{2}g & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 2g & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
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
E_1^{(0)} + E_2^{(0)} & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & E_1^{(0)} + E_2^{(1)} & 0 & g & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & E_1^{(0)} + E_2^{(2)} & 0 & \sqrt{2}g & 0 & 0 & 0 & 0 \\
0 & g & 0 & E_1^{(1)} + E_2^{(0)} & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & \sqrt{2}g & 0 & E_1^{(1)} + E_2^{(1)} & 0 & \sqrt{2}g & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & E_1^{(1)} + E_2^{(2)} & 0 & 2g & 0 \\
0 & 0 & 0 & 0 & \sqrt{2}g & 0 & E_1^{(2)} + E_2^{(0)} & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 2g & 0 & E_1^{(2)} + E_2^{(1)} & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & E_1^{(2)} + E_2^{(2)} \\
\end{pmatrix}
\end{aligned}
$$

## 調和振動子の場合

$E_1^{(n)} = \omega_1 n$ と $E_2^{(n)} = \omega_2 n$ とすると、

$$
\begin{aligned}
H &= \begin{pmatrix}
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & \omega_2 & 0 & g & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 2 \omega_2 & 0 & \sqrt{2}g & 0 & 0 & 0 & 0 \\
0 & g & 0 & \omega_1 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & \sqrt{2}g & 0 & \omega_1 + \omega_2 & 0 & \sqrt{2}g & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & \omega_1 + 2 \omega_2 & 0 & 2g & 0 \\
0 & 0 & 0 & 0 & \sqrt{2}g & 0 & 2 \omega_1 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 2g & 0 & 2 \omega_1 + \omega_2 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 2 \omega_1 + 2 \omega_2 \\
\end{pmatrix} \\
\end{aligned}
$$

となる。

これを対角化すると、$g \ll \Delta$ のもとで、固有値は

$$
\begin{aligned}
\lambda_1 &= 0 \\
\lambda_2 &= \omega_2 - \frac{g^2}{\Delta} \\
\lambda_3 &= 2 \omega_2 - \frac{2g^2}{\Delta} \\
\lambda_4 &= \omega_1 + \frac{g^2}{\Delta} \\
\lambda_5 &= \omega_1 + \omega_2 \\
\lambda_6 &= \omega_1 + 2 \omega_2 - \frac{4g^2}{\Delta} \\
\lambda_7 &= 2 \omega_1 + \frac{2g^2}{\Delta} \\
\lambda_8 &= 2 \omega_1 + \omega_2 + \frac{4g^2}{\Delta} \\
\lambda_9 &= 2 \omega_1 + 2 \omega_2 \\
\end{aligned}
$$

となる。

## トランズモンの場合

$$
E_1^{(n)} = \left( \omega_1 - \frac{\alpha_1}{2} \right) n + \frac{\alpha_1}{2} n^2
$$

$$
E_2^{(n)} = \left( \omega_2 - \frac{\alpha_2}{2} \right) n + \frac{\alpha_2}{2} n^2
$$

とすると、

$$
\begin{aligned}
H &= \begin{pmatrix}
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & \omega_2 & 0 & g & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 2 \omega_2 + \alpha_2 & 0 & \sqrt{2}g & 0 & 0 & 0 & 0 \\
0 & g & 0 & \omega_1 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & \sqrt{2}g & 0 & \omega_1 + \omega_2 & 0 & \sqrt{2}g & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & \omega_1 + 2 \omega_2 + \alpha_2 & 0 & 2g & 0 \\
0 & 0 & 0 & 0 & \sqrt{2}g & 0 & 2 \omega_1 + \alpha_1 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 2g & 0 & 2 \omega_1 + \omega_2 + \alpha_1 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 2 \omega_1 + 2 \omega_2 + \alpha_1 + \alpha_2 \\
\end{pmatrix} \\
\end{aligned}
$$
