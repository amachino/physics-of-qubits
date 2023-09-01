# 結合 2 量子系

## ハミルトニアン

$N$ 準位量子系と $M$ 準位量子系の間の結合を考えよう。相互作用のないときのハミルトニアンは、それぞれ

$$
\begin{aligned}
H_1 &= \sum_{k=0}^{M-1} E_1^{(k)} \ket{k}_1 \bra{k}_1 \\
&= \begin{pmatrix}
E_1^{(0)} & & & \\
& E_1^{(1)} & & \\
& & \ddots & \\
& & & E_1^{(M-1)}
\end{pmatrix} \\
H_2 &= \sum_{k=0}^{N-1} E_2^{(k)} \ket{k}_2 \bra{k}_2 \\
&= \begin{pmatrix}
E_2^{(0)} & & & \\
& E_2^{(1)} & & \\
& & \ddots & \\
& & & E_2^{(N-1)}
\end{pmatrix} \\
\end{aligned}
$$

と表されているとする。また、結合定数を $g$ として、相互作用項は

$$
\begin{aligned}
H_{\mathrm{int}} &= g
\sum_{k=0}^{M-1} \left( \sqrt{k+1} \ket{k+1}_1 \bra{k}_1
\right)
\otimes
\sum_{k=0}^{N-1} \left( \sqrt{k} \ket{k}_2 \bra{k+1}_2
\right) \\
&+ g
\sum_{k=0}^{M-1} \left( \sqrt{k} \ket{k}_1 \bra{k+1}_1
\right)
\otimes
\sum_{k=0}^{N-1} \left( \sqrt{k+1} \ket{k+1}_2 \bra{k}_2
\right)
\\
&= g
\begin{pmatrix}
0 & \sqrt{1} & & & \\
& 0 & \sqrt{2} & & \\
& & \ddots & \ddots & \\
& & & 0 & \sqrt{M-1} \\
& & & & 0 \\
\end{pmatrix}
\otimes
\begin{pmatrix}
0 & & & & \\
\sqrt{1} & 0 & & & \\
& \sqrt{2} & 0 & & \\
& & \ddots & \ddots & \\
& & & \sqrt{N-1} & 0 \\
\end{pmatrix} \\
&+ g
\begin{pmatrix}
0 & & & & \\
\sqrt{1} & 0 & & & \\
& \sqrt{2} & 0 & & \\
& & \ddots & \ddots & \\
& & & \sqrt{M-1} & 0 \\
\end{pmatrix}
\otimes
\begin{pmatrix}
0 & \sqrt{1} & & & \\
& 0 & \sqrt{2} & & \\
& & \ddots & \ddots & \\
& & & 0 & \sqrt{N-1} \\
& & & & 0 \\
\end{pmatrix}
\end{aligned}
$$

とする。このとき、全体のハミルトニアンは

$$
\begin{aligned}
H &= H_1 \otimes I_2
+ I_1 \otimes H_2
+ H_{\mathrm{int}}
\end{aligned}
$$

となる。
