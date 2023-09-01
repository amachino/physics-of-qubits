# 生成消滅演算子の行列表現

N 次元の生成・消滅演算子をそれぞれ $a^\dagger, a$ と書くことにすると、

$$
\begin{aligned}
a^\dagger \ket{n} &= \sqrt{n+1} \ket{n+1} \\
a \ket{n} &= \sqrt{n} \ket{n-1}
\end{aligned}
$$

であり、

$$
\begin{aligned}
a^\dagger &= \sum_{k=0}^{N-1} \sqrt{k+1} \ket{k+1} \bra{k} \\
&=
\begin{pmatrix}
0 & 0 & \cdots & 0 & 0 \\
\sqrt{1} & 0 & \cdots & 0 & 0 \\
0 & \sqrt{2} & \cdots & 0 & 0 \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & \cdots & \sqrt{N-1} & 0
\end{pmatrix}
\end{aligned}
$$

$$
\begin{aligned}
a &= \sum_{k=0}^{N-1} \sqrt{k} \ket{k} \bra{k+1} \\
&=
\begin{pmatrix}
0 & \sqrt{1} & 0 & \cdots & 0 \\
0 & 0 & \sqrt{2} & \cdots & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \cdots & \sqrt{N-1} \\
0 & 0 & 0 & \cdots & 0
\end{pmatrix}
\end{aligned}
$$

と表される。

$$
\begin{aligned}
a^\dagger a &=
\begin{pmatrix}
0 & 0 & \cdots & 0 & 0 \\
\sqrt{1} & 0 & \cdots & 0 & 0 \\
0 & \sqrt{2} & \cdots & 0 & 0 \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & \cdots & \sqrt{N-1} & 0
\end{pmatrix}
\begin{pmatrix}
0 & \sqrt{1} & 0 & \cdots & 0 \\
0 & 0 & \sqrt{2} & \cdots & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \cdots & \sqrt{N-1} \\
0 & 0 & 0 & \cdots & 0
\end{pmatrix}
\\
&=
\begin{pmatrix}
0 & 0 & 0 & \cdots & 0 \\
0 & 1 & 0 & \cdots & 0 \\
0 & 0 & 2 & \cdots & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \cdots & N-1
\end{pmatrix}
\end{aligned}
$$

$$
\begin{aligned}
a a^\dagger &=
\begin{pmatrix}
0 & \sqrt{1} & 0 & \cdots & 0 \\
0 & 0 & \sqrt{2} & \cdots & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \cdots & \sqrt{N-1} \\
0 & 0 & 0 & \cdots & 0
\end{pmatrix}
\begin{pmatrix}
0 & 0 & \cdots & 0 & 0 \\
\sqrt{1} & 0 & \cdots & 0 & 0 \\
0 & \sqrt{2} & \cdots & 0 & 0 \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & \cdots & \sqrt{N-1} & 0
\end{pmatrix}
\\
&=
\begin{pmatrix}
1 & 0 & 0 & \cdots & 0 \\
0 & 2 & 0 & \cdots & 0 \\
0 & 0 & 3 & \cdots & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \cdots & N
\end{pmatrix}
\end{aligned}
$$

であるから、

$$
\begin{aligned}
a^\dagger a \ket{n} &= n \ket{n} \\
a a^\dagger \ket{n} &= (n+1) \ket{n} \\
\end{aligned}
$$

である。

$$
\begin{aligned}
a a^\dagger \ket{n} &= (a^\dagger a + 1)\ket{n} \\
(a^\dagger a)^2 \ket{n} &= n^2 \ket{n}
\end{aligned}
$$

また、

$$
\begin{aligned}
(a^\dagger)^2 &=
\begin{pmatrix}
0 & 0 & \cdots & 0 & 0 & 0 \\
0 & 0 & \cdots & 0 & 0 & 0 \\
\sqrt{1 \cdot 2} & 0 & \cdots & 0 & 0 & 0 \\
0 & \sqrt{2 \cdot 3} & \cdots & 0 & 0 & 0 \\
\vdots & \vdots & \ddots & \vdots & \vdots & \vdots \\
0 & 0 & \cdots & \sqrt{(N-2)(N-1)} & 0 & 0 \\
\end{pmatrix}
\\
a^2 &=
\begin{pmatrix}
0 & 0 & \sqrt{1 \cdot 2} & 0 & \cdots & 0 \\
0 & 0 & 0 & \sqrt{2 \cdot 3} & \cdots & 0 \\
\vdots & \vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & 0 & \cdots & \sqrt{(N-2)(N-1)} \\
0 & 0 & 0 & 0 & \cdots & 0 \\
0 & 0 & 0 & 0 & \cdots & 0 \\
\end{pmatrix}
\end{aligned}
$$

であり、

$$
\begin{aligned}
(a^\dagger)^2 a^2 &=
\begin{pmatrix}
0 & 0 & 0 & 0 & \cdots & 0 \\
0 & 1 \cdot 0 & 0 & 0 & \cdots & 0 \\
0 & 0 & 2 \cdot 1 & 0 & \cdots & 0 \\
0 & 0 & 0 & 3 \cdot 4 & \cdots & 0 \\
\vdots & \vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & 0 & \cdots & (N-2)(N-1)
\end{pmatrix}
\end{aligned}
$$

となるから、

$$
\begin{aligned}
(a^\dagger)^2 a^2 \ket{n} &= (n-1) n \ket{n} \\
&= n^2 \ket{n} - n \ket{n} \\
&= (a^\dagger a)^2 \ket{n} - (a^\dagger a) \ket{n}
\end{aligned}
$$

の関係がある。

$$
(a^\dagger)^2 a^2 = a^\dagger a^\dagger a a
$$

と

$$
(a^\dagger a)^2 = a^\dagger a a^\dagger a
$$

は等しくないことに注意しよう。

これは、$a$ と $a^\dagger$ が、交換関係

$$
[a, a^\dagger] = aa^\dagger - a^\dagger a = I
$$

をもち、可換ではないことに起因する。
