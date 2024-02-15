---
title: Piecewise Constant Hamiltonian
date: 2024-02-15
authors:
  - name: Akinori Machino
---

# 区分定数ハミルトニアン

系のハミルトニアンが、時間に依存するが、時間によって区分的に定数であるとする。

$$
H(t) = H_n \quad (t_{n-1} \le t \le t_{n})
$$
$$
n = 1, 2, \dots
$$

つまり、時間 $t$ が $t_0 \le t \le t_1$ の間は $H_1$ 、$t_1 \le t \le t_2$ の間は $H_2$ 、というように、時間経過とともにハミルトニアンが階段状に変化する状況を考える。

$\Delta t_n = t_n - t_{n-1}$ とすると、時間発展演算子 $U(t_n, t_{n-1})$ は

$$
U(t_n, t_{n-1}) = e^{-i H_n \Delta t_n}
$$

であるので、時間 $t_0$ から $t_n$ までの時間発展演算子 $U(t_n, t_0)$ は

$$
\begin{aligned}
U(t_n, t_0) &= U(t_n, t_{n-1}) U(t_{n-1}, t_{n-2}) \cdots U(t_1, t_0)
\\
&= e^{-i H_n \Delta t_n} e^{-i H_{n-1} \Delta t_{n-1}} \cdots e^{-i H_1 \Delta t_1}
\end{aligned}
$$

と表される。

$\{H_n\}$ の要素がすべて交換する場合には、

$$
\begin{aligned}
U(t_n, t_0) &= e^{-i H_n \Delta t_n} e^{-i H_{n-1} \Delta t_{n-1}} \cdots e^{-i H_1 \Delta t_1}
\\
&= e^{-i \left( H_n \Delta t_n + H_{n-1} \Delta t_{n-1} + \cdots + H_1 \Delta t_1 \right)}
\end{aligned}
$$

とできるが、一般には交換しないことに注意する。

すべて交換する具体的な例としては、量子ビットを I 成分のみのパルス

$$
H(t) = \frac{I(t)}{2} \sigma_x
$$
$$
I(t) = I_n \quad (t_{n-1} \le t \le t_{n})
$$

で操作する場合が挙げられる。

I/Q 両成分を含むパルスを用いる場合

$$
H(t) = \frac{I(t)}{2} \sigma_x + \frac{Q(t)}{2} \sigma_y
$$

には、$\sigma_x$ と $\sigma_y$ が交換しないため、指数の肩をまとめることはできない。

いずれの場合においても、区分定数ハミルトニアンの時間発展演算子 $U(t_n, t_0)$ は、微分方程式（シュレーディンガー方程式）を数値的に解くは必要なく、高々 $n$ 個の行列指数関数の計算で求めることができる。