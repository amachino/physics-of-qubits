# 結合 2 量子系

## ハミルトニアン

2 つの量子系 $H_1, H_2$ が結合する状況を考えよう。

$H_1$ は $M$ 次元、 $H_2$ は $N$ 次元で表せるものとし、単独のハミルトニアンは、それぞれ

$$
\begin{aligned}
H_1 &= \sum_{n=0}^{M-1} E_1^{(n)} \ket{n}_1 \bra{n}_1 \\
&= \begin{pmatrix}
E_1^{(0)} & 0 & \cdots & 0 \\
0 & E_1^{(1)} & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & E_1^{(M-1)}
\end{pmatrix} \\
H_2 &= \sum_{n=0}^{N-1} E_2^{(n)} \ket{n}_2 \bra{n}_2 \\
&= \begin{pmatrix}
E_2^{(0)} & 0 & \cdots & 0 \\
0 & E_2^{(1)} & \cdots & 0 \\
\vdots & \vdots & \ddots & \vdots \\
0 & 0 & \cdots & E_2^{(N-1)}
\end{pmatrix}
\end{aligned}
$$

と表されているとする。

例えば、調和振動子であれば、

$$
\begin{aligned}
E^{(n)} &= \omega n
\end{aligned}
$$

トランズモンであれば、

$$
\begin{aligned}
E^{(n)} &= \left( \omega - \frac{\alpha}{2} \right) n + \frac{\alpha}{2} n^2
\end{aligned}
$$

である。

また、結合定数を $g$ として、相互作用項は

$$
\begin{aligned}
H_{\mathrm{int}} &= g
\sum_{n=0}^{M-2} \left( \sqrt{n+1} \ket{n+1}_1 \bra{n}_1
\right)
\otimes
\sum_{n=0}^{N-2} \left( \sqrt{n+1} \ket{n}_2 \bra{n+1}_2
\right) \\
&+ g
\sum_{n=0}^{M-2} \left( \sqrt{n+1} \ket{n}_1 \bra{n+1}_1
\right)
\otimes
\sum_{n=0}^{N-2} \left( \sqrt{n+1} \ket{n+1}_2 \bra{n}_2
\right)
\\
&= g
\begin{pmatrix}
0 & 0 & \cdots & 0 & 0 \\
\sqrt{1} & 0 & \cdots & 0 & 0 \\
0 & \sqrt{2} & \cdots & 0 & 0 \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & \cdots & \sqrt{M-1} & 0
\end{pmatrix}
\otimes
\begin{pmatrix}
0 & \sqrt{1} & 0 & \cdots & 0 \\
0 & 0 & \sqrt{2} & 0 & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \cdots & \sqrt{N-1} \\
0 & 0 & 0 & \cdots & 0
\end{pmatrix}
\\
&+ g
\begin{pmatrix}
0 & \sqrt{1} & 0 & \cdots & 0 \\
0 & 0 & \sqrt{2} & \cdots & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \cdots & \sqrt{M-1} \\
0 & 0 & 0 & \cdots & 0
\end{pmatrix}
\otimes
\begin{pmatrix}
0 & 0 & \cdots & 0 & 0 \\
\sqrt{1} & 0 & \cdots & 0 & 0 \\
0 & \sqrt{2} & \cdots & 0 & 0 \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & \cdots & \sqrt{N-1} & 0
\end{pmatrix}
\end{aligned}
$$

であるとする。

このとき、全体のハミルトニアンは、

$$
\begin{aligned}
H &= H_1 \otimes I_2
+ I_1 \otimes H_2
+ H_{\mathrm{int}}
\end{aligned}
$$

で表され、 $M \times N$ 次元の正方行列となる。
