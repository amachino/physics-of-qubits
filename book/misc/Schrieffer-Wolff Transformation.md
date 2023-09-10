# Schrieffer-Wolff 変換

2 つの量子系 $H_1, H_2$ が微小な結合定数 $g$ で結合している状況を考えよう。

$$
\begin{aligned}
H &= H_1 \otimes I_2
+ I_1 \otimes H_2
+ H_{\mathrm{int}}
\end{aligned}
$$

$H_1, H_2$ は

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

と対角化されており、相互作用項 $H_{\mathrm{int}}$ は

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

という形で $g$ の 1 次の非対角項成分を持っている。

$H_1 \otimes I_2 + I_1 \otimes H_2 = H_0$ 、 $H_{\mathrm{int}} = V$ と置き直そう。

$$
H = H_0 + V
$$

$H_0$ は対角行列であり、 $V$ は $g$ の 1 次の非対角行列である。

$H_0$ の固有値、固有ベクトルは $\ket{n}, E_n$ とする。

ここで、ユニタリ行列 $U = e^{-S}$ （ $S$ は $g$ の 1 次の反エルミート行列）を用いて、このハミルトニアン $H$ の非対角成分から $g$ の 1 次項を取り除くことを考える。

元の基底 $\ket{n}$ は、 $U$ によって $\ket{n}' = U \ket{n}$ と変換され、 $H$ は

$$
\begin{aligned}
H' &= U H U^\dagger \\
&= e^{-S} H e^{S} \\
&= e^{-S} \left(H_0 + V \right) e^{S} \\
&= e^{-S} H_0 e^{S} + e^{-S} V e^{S} \\
&= H'_{0} + V'
\end{aligned}
$$

と変換されるとする。

つまり、 $H'_{0}$ が対角行列、 $V'$ が $g$ の 2 次以降の項のみを含むような $S$ を探したい。

Baker-Campbell-Hausdorff 公式

$$
\begin{aligned}
e^{-S} H e^{S} = H + [H, S] + \frac{1}{2} [[H, S], S] + \cdots \\
\end{aligned}
$$

を用いれば、

$$
\begin{aligned}
H' &= e^{-S} H e^{S} \\
&= e^{-S} \left(H_0 + V \right) e^{S} \\
&= H_0 + V + [H_0, S] + [V, S] + \frac{1}{2} [[H_0, S], S] + \frac{1}{2} [[V, S], S] + \cdots \\
&= H_0+\underbrace{V+\left[H_0, S\right]}_{O(g)}+\underbrace{[V, S]+\frac{1}{2}\left[\left[H_0, S\right], S\right]}_{O\left(g^2\right)}+O\left(g^3\right)

\end{aligned}
$$

であるから、

$$
V + [H_0, S] = 0
$$

となるように $S$ を選べば要件は満たされる。

このとき、

$$
\begin{aligned}
H' &= H_0+V+\left[H_0, S\right]+[V, S]+\frac{1}{2}\left[\left[H_0, S\right], S\right]+O\left(g^3\right) \\
&= H_0+0+[V, S]+\frac{1}{2}\left[-V, S\right]+O\left(g^3\right) \\
&= H_0+\frac{1}{2}\left[V, S\right]+O\left(g^3\right)
\end{aligned}
$$

であり、 $H'$ は $g$ の 1 次項を含まない。

$$
\begin{aligned}
H_0 &= \sum_{n} E_n \ket{n} \bra{n} \\
S &= \sum_{m, n} S_{mn} \ket{m} \bra{n} \\
\end{aligned}
$$

とすれば、

$$
\begin{aligned}
\left[H_0, S\right]
& = H_0 S - S H_0 \\
&= E_m \sum_{m, n} S_{mn} \ket{m} \bra{n}
- E_n \sum_{m, n} S_{mn} \ket{m} \bra{n} \\
&= \sum_{m, n} \left( E_m - E_n \right) S_{mn} \ket{m} \bra{n} \\
\end{aligned}
$$

であるから、

$$
\begin{aligned}
V &= \sum_{m, n} V_{mn} \ket{m} \bra{n} \\
\end{aligned}
$$

とすれば、

$$
\begin{aligned}
S_{mn} = \frac{V_{mn}}{E_n - E_m}
\end{aligned}
$$

となる。

つまり、 $S$ は $V$ の各成分の値を $E_n - E_m$ で割ったものになる。

## 例 1: qubit-qubit

$$
\begin{aligned}
H_0 &=
\begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & \omega_2 & g & 0 \\
0 & g & \omega_1 & 0 \\
0 & 0 & 0 & \omega_1 + \omega_2 \\
\end{pmatrix} \\

V &= \begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & 0 & g & 0 \\
0 & g & 0 & 0 \\
0 & 0 & 0 & 0 \\
\end{pmatrix}
\end{aligned}
$$

であれば、 $\Delta = \omega_1 - \omega_2$ として、

$$
\begin{aligned}
S &= \begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & 0 & \frac{g}{\Delta} & 0 \\
0 & -\frac{g}{\Delta} & 0 & 0 \\
0 & 0 & 0 & 0 \\
\end{pmatrix}
\end{aligned}
$$

となる。

$$
\begin{aligned}
\left[ V, S \right]
&= \begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & -\frac{2g^2}{\Delta} & 0 & 0 \\
0 & 0 & \frac{2g^2}{\Delta} & 0 \\
0 & 0 & 0 & 0 \\
\end{pmatrix}
\end{aligned}
$$

であるから、

$$
\begin{aligned}
H' &= H_0+\frac{1}{2}\left[V, S\right]+O\left(g^3\right) \\
&=
\begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & \omega_2 & g & 0 \\
0 & g & \omega_1 & 0 \\
0 & 0 & 0 & \omega_1 + \omega_2 \\
\end{pmatrix} +
\begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & -\frac{g^2}{\Delta} & 0 & 0 \\
0 & 0 & \frac{g^2}{\Delta} & 0 \\
0 & 0 & 0 & 0 \\
\end{pmatrix} + O\left(g^3\right) \\
&= \begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & \omega_2 - \frac{g^2}{\Delta} & 0 & 0 \\
0 & 0 & \omega_1 + \frac{g^2}{\Delta} & 0 \\
0 & 0 & 0 & \omega_1 + \omega_2 \\
\end{pmatrix} + O\left(g^3\right)
\end{aligned}
$$

$O\left(g^3\right)$ を除いた対角行列は、 $H$ を厳密に対角化した後に、 $\frac{g^2}{\Delta^2} \ll 1$ として近似したものと一致する。

## 例 2: qutrit-qutrit

$$
\begin{aligned}
H_0 &=
\begin{pmatrix}
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & \omega_2 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 2 \omega_2 + \alpha_2 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & \omega_1 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & \omega_1 + \omega_2 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & \omega_1 + 2 \omega_2 + \alpha_2 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 2 \omega_1 + \alpha_1 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 2 \omega_1 + \alpha_1 + \omega_2 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 2 \omega_1 + 2 \omega_2 + \alpha_1 + \alpha_2 \\
\end{pmatrix} \\

V &= \begin{pmatrix}
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & g & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & \sqrt{2}g & 0 & 0 & 0 & 0 \\
0 & g & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & \sqrt{2}g & 0 & 0 & 0 & \sqrt{2}g & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 2g & 0 \\
0 & 0 & 0 & 0 & \sqrt{2}g & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 2g & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
\end{pmatrix} \\
\end{aligned}
$$

であれば、 $\Delta = \omega_1 - \omega_2$ として、

$$
\begin{aligned}
S &= \begin{pmatrix}
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & \frac{g}{\Delta} & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & \frac{\sqrt{2}g}{\Delta - \alpha_2} & 0 & 0 & 0 & 0 \\
0 & -\frac{g}{\Delta} & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & -\frac{\sqrt{2}g}{\Delta - \alpha_2} & 0 & 0 & 0 & \frac{\sqrt{2}g}{\Delta + \alpha_1} & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & \frac{2g}{\Delta + \alpha_1 - \alpha_2} & 0 \\
0 & 0 & 0 & 0 & -\frac{\sqrt{2}g}{\Delta + \alpha_1} & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & -\frac{2g}{\Delta + \alpha_1 - \alpha_2} & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
\end{pmatrix} \\
\end{aligned}
$$

となる。

$$
\begin{aligned}
\left[ V, S \right] &= \begin{pmatrix}
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & -\frac{2g^2}{\Delta} & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & -\frac{4g^2}{\Delta - \alpha_2} & 0 & 0 & 0 & \frac{2g^2}{\Delta + \alpha_1} - \frac{2g^2}{\Delta - \alpha_2} & 0 & 0 \\
0 & 0 & 0 & \frac{2g^2}{\Delta} & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & -\frac{4g^2}{\Delta + \alpha_1} + \frac{4g^2}{\Delta - \alpha_2} & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & -\frac{8g^2}{\Delta + \alpha_1 - \alpha_2} & 0 & 0 & 0 \\
0 & 0 & \frac{2g^2}{\Delta + \alpha_1} - \frac{2g^2}{\Delta - \alpha_2} & 0 & 0 & 0 & \frac{4g^2}{\Delta + \alpha_1} & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & \frac{8g^2}{\Delta + \alpha_1 - \alpha_2} & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
\end{pmatrix}
\end{aligned}
$$

であるから、

$$
\begin{aligned}
H' &= H_0+\frac{1}{2}\left[V, S\right]+O\left(g^3\right) \\
&=
\begin{pmatrix}
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & \omega_2 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 2 \omega_2 + \alpha_2 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & \omega_1 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & \omega_1 + \omega_2 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & \omega_1 + 2 \omega_2 + \alpha_2 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 2 \omega_1 + \alpha_1 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 2 \omega_1 + \alpha_1 + \omega_2& 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 2 \omega_1 + 2 \omega_2 + \alpha_1 + \alpha_2 \\
\end{pmatrix} \\
&+
\begin{pmatrix}
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & -\frac{g^2}{\Delta} & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & -\frac{2g^2}{\Delta - \alpha_2} & 0 & 0 & 0 & \frac{g^2}{\Delta + \alpha_1} - \frac{g^2}{\Delta - \alpha_2} & 0 & 0 \\
0 & 0 & 0 & \frac{g^2}{\Delta} & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & -\frac{2g^2}{\Delta + \alpha_1} + \frac{2g^2}{\Delta - \alpha_2} & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & -\frac{4g^2}{\Delta + \alpha_1 - \alpha_2} & 0 & 0 & 0 \\
0 & 0 & \frac{g^2}{\Delta + \alpha_1} - \frac{g^2}{\Delta - \alpha_2} & 0 & 0 & 0 & \frac{2g^2}{\Delta + \alpha_1} & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & \frac{4g^2}{\Delta + \alpha_1 - \alpha_2} & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
\end{pmatrix} \\
&+ O\left(g^3\right) \\
&= \begin{pmatrix}
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & \omega_2 - \frac{g^2}{\Delta} & 0 & 0 & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 2 \omega_2 + \alpha_2 - \frac{2g^2}{\Delta - \alpha_2} & 0 & 0 & 0 & \frac{g^2}{\Delta + \alpha_1} - \frac{g^2}{\Delta - \alpha_2} & 0 & 0 \\
0 & 0 & 0 & \omega_1 + \frac{g^2}{\Delta} & 0 & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & \omega_1 + \omega_2 - \frac{2g^2}{\Delta + \alpha_1} + \frac{2g^2}{\Delta - \alpha_2} & 0 & 0 & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & \omega_1 + 2 \omega_2 + \alpha_2 - \frac{4g^2}{\Delta + \alpha_1 - \alpha_2} & 0 & 0 & 0 \\
0 & 0 & \frac{g^2}{\Delta + \alpha_1} - \frac{g^2}{\Delta - \alpha_2} & 0 & 0 & 0 & 2 \omega_1 + \alpha_1 + \frac{2g^2}{\Delta + \alpha_1} & 0 & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 2 \omega_1 + \alpha_1 + \omega_2 + \frac{4g^2}{\Delta + \alpha_1 - \alpha_2} & 0 \\
0 & 0 & 0 & 0 & 0 & 0 & 0 & 0 & 2 \omega_1 + 2 \omega_2 + \alpha_1 + \alpha_2 \\
\end{pmatrix} \\
&+ O\left(g^3\right)
\end{aligned}
$$

この行列から、高次準位を取り除いた $H'$ は、

$$
\begin{aligned}
H' &= \begin{pmatrix}
0 & 0 & 0 & 0 \\
0 & \omega_2 - \frac{g^2}{\Delta} & 0 & 0 \\
0 & 0 & \omega_1 + \frac{g^2}{\Delta} & 0 \\
0 & 0 & 0 & \omega_1 + \omega_2 + \frac{2g^2(\alpha_1 + \alpha_2)}{(\Delta + \alpha_1)(\Delta - \alpha_2)}
\end{pmatrix} \\
\end{aligned}
$$

であり、 $H'$ を

$$
\begin{aligned}
H' &= c_{II} \cdot I \otimes I + c_{ZI} \cdot Z \otimes I + c_{IZ} \cdot I \otimes Z + c_{ZZ} \cdot Z \otimes Z
\end{aligned}
$$

のように ${II, IZ, ZI, ZZ}$ で展開すると、

$$
\begin{aligned}
c_{II} &= 
\frac{1}{2} \left( \omega_1 + \omega_2 + \xi \right) \\
c_{IZ} &=
-\frac{1}{2} \left( \omega_2 - \frac{g^2}{\Delta} + \xi \right) \\
c_{ZI} &=
- \frac{1}{2} \left( \omega_1 + \frac{g^2}{\Delta} + \xi \right) \\
c_{ZZ} &= \frac{1}{2} \xi
\end{aligned}
$$

ただし、

$$
\xi = \frac{g^2(\alpha_1 + \alpha_2)}{(\Delta + \alpha_1)(\Delta - \alpha_2)}
$$

である。