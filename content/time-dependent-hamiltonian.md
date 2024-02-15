---
title: Time-dependent Hamiltonian
date: 2024-02-15
authors:
  - name: Akinori Machino
---

# 時間に依存するハミルトニアン

系のハミルトニアンが、時間に依存しない $H$ のみであれば、シュレーディンガー方程式

$$
\frac{d}{dt} U(t) = -i H U(t) \tag{1}
$$

は厳密に解くことができ、時間発展演算子 $U(t)$

$$
U(t) = e^{-i H t} \tag{2}
$$

によって、系の時間発展を完全を記述することができる。

一方、時間に依存するハミルトニアン $H(t)$ の場合、

$$
\frac{d}{dt} U(t) = -i H(t) U(t) \tag{3}
$$

は一般に解けず、時間順序積 $\mathcal{T}$ を用いて

$$
U(t) = \mathcal{T} \exp \left( -i \int_0^t dt' H(t') \right) \tag{4}
$$

と表されることが知られている。まずこれを確認しよう。

$(3)$ 式を形式的に積分すると、$t=0$ で $U(0) = I$ であることを用いて

$$
U(t) = I - i \int_0^t dt_1 H(t_1) U(t_1) \tag{5}
$$

となる。この $(5)$ 式の $U(t_1)$ に $(5)$ 式自身を代入すると

$$
\begin{aligned}
U(t) &= I -i \int_0^t dt_1 H(t_1) \left( I -i \int_0^{t_1} dt_2 H(t_2) U(t_2) \right)
\\
&= I -i \int_0^t dt_1 H(t_1) - \int_0^t dt_1 \int_0^{t_1} dt_2 H(t_1) H(t_2) U(t_2)
\end{aligned}
$$

これを繰り返すと、

$$
\begin{aligned}
U(t) &= I
\\
&+ (-i) \int_0^t dt_1 H(t_1)
\\
&+ (-i)^2 \int_0^t dt_1 \int_0^{t_1} dt_2 H(t_1) H(t_2)
\\
&+ (-i)^3 \int_0^t dt_1 \int_0^{t_1} dt_2 \int_0^{t_2} dt_3 H(t_1) H(t_2) H(t_3)
\\
&+ \cdots
\\
&+ (-i)^n \int_0^t dt_1 \int_0^{t_1} dt_2 \cdots \int_0^{t_{n-1}} dt_n H(t_1) H(t_2) \cdots H(t_n) \tag{6}
\end{aligned}
$$

となる。これをダイソン級数 (Dyson series) と呼ぶ。

時間の関係は $t \ge t_1 \ge t_2 \ge \cdots \ge t_n \ge 0$ であることに注意すると、この積分は時間順序積 $\mathcal{T}$ を用いて

$$
\begin{aligned}
U(t) &= I
\\
&+ (-i) \int_0^t dt_1 H(t_1)
\\
&+ \mathcal{T} \frac{(-i)^2}{2!} \iint_0^t dt_1 dt_2 H(t_1) H(t_2)
\\
&+ \mathcal{T} \frac{(-i)^3}{3!} \iiint_0^t dt_1 dt_2 dt_3 H(t_1) H(t_2) H(t_3)
\\
&+ \cdots
\\
&+ \mathcal{T} \frac{(-i)^n}{n!} \iint \cdots \int_0^t dt_1 dt_2 \cdots dt_n H(t_1) H(t_2) \cdots H(t_n)
\\
&= I - i \int_0^t dt' H(t')
\\
&+ \mathcal{T} \frac{1}{2!} \left(-i \int_0^t dt' H(t') \right)^2
\\
&+ \mathcal{T} \frac{1}{3!} \left(-i \int_0^t dt' H(t') \right)^3
\\
&+ \cdots
\\
&+ \mathcal{T} \frac{1}{n!} \left(-i \int_0^t dt' H(t') \right)^n
\\
&= \mathcal{T} \sum_{n} \frac{1}{n!} \left( -i \int_0^t dt' H(t') \right)^n
\end{aligned}
$$

と表すことができる。 $n \to \infty$ とした極限で、指数関数の級数展開の形を用いることで $(4)$ 式が得られる。

時間順序積を用いた表式 $(4)$ は見た目上シンプルだが、実際の計算は

$$
U(t) = I + \sum_{n=0}^\infty (-i)^n \int_0^t dt_1 \int_0^{t_1} dt_2 \cdots \int_0^{t_{n-1}} dt_n H(t_1) H(t_2) \cdots H(t_n) \tag{7}
$$

を用いて、有限の $n$ 次までの積分によって近似的に計算することになるだろう。