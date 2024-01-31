---
title: Ladder Operators
date: 2023-09-04
authors:
  - name: Akinori Machino
---

# 生成消滅演算子の行列表現

$N$ 個の状態ベクトル

$$
\ket{0} =
\begin{pmatrix}
1 \\
0 \\
\vdots \\
0
\end{pmatrix},\quad
\ket{1} =
\begin{pmatrix}
0 \\
1 \\
\vdots \\
0
\end{pmatrix},\quad\dots,\quad
\ket{N-1} =
\begin{pmatrix}
0 \\
0 \\
\vdots \\
1
\end{pmatrix}
$$

が張る $N$ 次元のベクトル空間を考える。

このベクトル空間において、演算子 $\hat{O}$ は $N \times N$ 行列で表現できる。

$$
\begin{aligned}
\hat{O} =
\begin{pmatrix}
\langle 0 | \hat{O} | 0 \rangle & \langle 0 | \hat{O} | 1 \rangle & \cdots & \langle 0 | \hat{O} | N-1 \rangle \\
\langle 1 | \hat{O} | 0 \rangle & \langle 1 | \hat{O} | 1 \rangle & \cdots & \langle 1 | \hat{O} | N-1 \rangle \\
\vdots & \vdots & \ddots & \vdots \\
\langle N-1 | \hat{O} | 0 \rangle & \langle N-1 | \hat{O} | 1 \rangle & \cdots & \langle N-1 | \hat{O} | N-1 \rangle \\
\end{pmatrix}
\end{aligned}
$$

このとき、 $|i \rangle \langle j|$ は、$i$ 行 $j$ 列の成分が $1$ で他が $0$ の行列になるから、 $(i, j)$ 成分が $O_{ij}$ で表される行列は

$$
\begin{aligned}
\hat{O} = \sum_{i, j} O_{ij} |i \rangle \langle j|
\end{aligned}
$$

と書くこともできる。

さて、この $N$ 次元ベクトル空間で、生成消滅演算子 $\hat{a}, \hat{a}^\dagger$ を行列表記してみよう。

消滅演算子 $\hat{a}$ は状態を $1$ 下げ、生成演算子 $\hat{a}^\dagger$ は状態を $1$ 上げる演算子であり、

$$
\begin{aligned}
\hat{a} \ket{n} &=
\begin{cases}
0 & \text{if } n = 0 \\
\sqrt{n} \ket{n-1} & \text{if } n \in \{ 1, \cdots, N-1 \}
\end{cases}\
\\
\hat{a}^\dagger \ket{n} &=
\begin{cases}
\sqrt{n+1} \ket{n+1} & \text{if } n \in \{0, 1, \cdots, N-2\} \\
0 & \text{if } n = N-1
\end{cases}
\end{aligned}
$$

を満たす。したがって、

$$
\begin{aligned}
\hat{a}
&=
\begin{pmatrix}
0 & \sqrt{1} & 0 & \cdots & 0 \\
0 & 0 & \sqrt{2} & \cdots & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \cdots & \sqrt{N-1} \\
0 & 0 & 0 & \cdots & 0
\end{pmatrix} \\
&= \sum_{n=0}^{N-2} \sqrt{n+1} \ket{n} \bra{n+1}
\end{aligned}
$$

$$
\begin{aligned}
\hat{a}^\dagger
&=
\begin{pmatrix}
0 & 0 & \cdots & 0 & 0 \\
\sqrt{1} & 0 & \cdots & 0 & 0 \\
0 & \sqrt{2} & \cdots & 0 & 0 \\
\vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & \cdots & \sqrt{N-1} & 0
\end{pmatrix} \\
&= \sum_{n=0}^{N-2} \sqrt{n+1} \ket{n+1} \bra{n}
\end{aligned}
$$

と表すことができる。

$$
\begin{aligned}
\hat{a} \hat{a}^\dagger &=
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
1 & 0 & 0 & \cdots & 0 & 0 \\
0 & 2 & 0 & \cdots & 0 & 0 \\
0 & 0 & 3 & \cdots & 0 & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \cdots & N-1 & 0 \\
0 & 0 & 0 & \cdots & 0 & 0
\end{pmatrix} \\
&= \sum_{n=0}^{N-2} (n+1) \ket{n} \bra{n}
\end{aligned}
$$

$$
\begin{aligned}
\hat{a}^\dagger \hat{a} &=
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
0 & 0 & 0 & \cdots & 0 & 0 \\
0 & 1 & 0 & \cdots & 0 & 0 \\
0 & 0 & 2 & \cdots & 0 & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & 0 & \cdots & N-2 & 0 \\
0 & 0 & 0 & \cdots & 0 & N-1
\end{pmatrix} \\
&= \sum_{n=0}^{N-1} n \ket{n} \bra{n}
\end{aligned}
$$

であるから、

$$
\begin{aligned}
\hat{a} \hat{a}^\dagger - \hat{a}^\dagger \hat{a} &=
\begin{pmatrix}
1 & 0 & 0 & \cdots & 0 & 0 \\
0 & 2 & 0 & \cdots & 0 & 0 \\
0 & 0 & 3 & \cdots & 0 & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \cdots & N-1 & 0 \\
0 & 0 & 0 & \cdots & 0 & 0
\end{pmatrix}
-
\begin{pmatrix}
0 & 0 & 0 & \cdots & 0 & 0 \\
0 & 1 & 0 & \cdots & 0 & 0 \\
0 & 0 & 2 & \cdots & 0 & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & 0 & \cdots & N-2 & 0 \\
0 & 0 & 0 & \cdots & 0 & N-1
\end{pmatrix} \\
&=
\begin{pmatrix}
1 & 0 & 0 & \cdots & 0 & 0 \\
0 & 1 & 0 & \cdots & 0 & 0 \\
0 & 0 & 1 & \cdots & 0 & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & 0 & \cdots & 1 & 0 \\
0 & 0 & 0 & \cdots & 0 & 1-N
\end{pmatrix} \\
&=
1 - N \ket{N-1} \bra{N-1}
\end{aligned}
$$

である。

有限の $N \times N$ 行列で表現したとき、 $\hat{a} \hat{a}^\dagger - \hat{a}^\dagger \hat{a} = 1$ とはならないことに注意しよう。

$$
\begin{aligned}
\hat{a}^\dagger \hat{a} \ket{n} &= n \ket{n} \\
(\hat{a}^\dagger \hat{a})^2 \ket{n} &= n^2 \ket{n}
\\
\end{aligned}
$$

の関係はいつでも使えるが、

$$
\begin{aligned}
\hat{a} \hat{a}^\dagger \ket{n} &= (n+1) \ket{n} \\
&= (\hat{a}^\dagger \hat{a} + 1)\ket{n}
\end{aligned}
$$

の関係は $n \in \{0, 1, \cdots, N-2\}$ の範囲でしか使えない。

$\ket{N-1}$ に $\hat{a} \hat{a}^\dagger$ を作用させると、

$$
\begin{aligned}
\hat{a} \hat{a}^\dagger \ket{N-1} &= 0 \\
&= (\hat{a}^\dagger \hat{a} + 1-N)\ket{N-1}
\end{aligned}
$$

となる。

次に、生成消滅演算子を連続して作用させるとどうなるかを考えてみよう。

$$
\begin{aligned}
\hat{a}^2 &=
\begin{pmatrix}
0 & 0 & \sqrt{1 \cdot 2} & 0 & \cdots & 0 \\
0 & 0 & 0 & \sqrt{2 \cdot 3} & \cdots & 0 \\
\vdots & \vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & 0 & \cdots & \sqrt{(N-2)(N-1)} \\
0 & 0 & 0 & 0 & \cdots & 0 \\
0 & 0 & 0 & 0 & \cdots & 0 \\
\end{pmatrix} \\
&= \sum_{n=0}^{N-3} \sqrt{(n+1)(n+2)} \ket{n} \bra{n+2}
\\
(\hat{a}^\dagger)^2 &=
\begin{pmatrix}
0 & 0 & \cdots & 0 & 0 & 0 \\
0 & 0 & \cdots & 0 & 0 & 0 \\
\sqrt{1 \cdot 2} & 0 & \cdots & 0 & 0 & 0 \\
0 & \sqrt{2 \cdot 3} & \cdots & 0 & 0 & 0 \\
\vdots & \vdots & \ddots & \vdots & \vdots & \vdots \\
0 & 0 & \cdots & \sqrt{(N-2)(N-1)} & 0 & 0 \\
\end{pmatrix} \\
&= \sum_{n=0}^{N-3} \sqrt{(n+1)(n+2)} \ket{n+2} \bra{n}
\end{aligned}
$$

であり、

$$
\begin{aligned}
(\hat{a}^\dagger)^2 \hat{a}^2 &=
\begin{pmatrix}
0 & 0 & 0 & 0 & \cdots & 0 \\
0 & 0 \cdot 1 & 0 & 0 & \cdots & 0 \\
0 & 0 & 1 \cdot 2 & 0 & \cdots & 0 \\
0 & 0 & 0 & 2 \cdot 3 & \cdots & 0 \\
\vdots & \vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & 0 & \cdots & (N-2)(N-1)
\end{pmatrix} \\
&= \sum_{n=0}^{N-1} (n-1)n \ket{n} \bra{n}
\end{aligned}
$$

となるから、

$$
\begin{aligned}
(\hat{a}^\dagger)^2 \hat{a}^2 \ket{n} &= (n-1) n \ket{n} \\
&= n^2 \ket{n} - n \ket{n} \\
&= (\hat{a}^\dagger \hat{a})^2 \ket{n} - \hat{a}^\dagger \hat{a} \ket{n}
\end{aligned}
$$

の関係がある。 $\hat{a}$ と $\hat{a}^\dagger$ は可換ではないので、

$$
(\hat{a}^\dagger)^2 \hat{a}^2 = \hat{a}^\dagger \hat{a}^\dagger \hat{a} \hat{a}
$$

と

$$
(\hat{a}^\dagger \hat{a})^2 = \hat{a}^\dagger \hat{a} \hat{a}^\dagger \hat{a}
$$

は等しくないことに注意が必要である。

また、 $\ket{n}$ に対して消滅演算子 $\hat{a}$ を $n$ 回連続して作用させれば、

$$
\begin{aligned}
\hat{a}^{n}\ket{n} = \sqrt{n!} \ket{0}
\end{aligned}
$$

となる。
