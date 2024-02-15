---
title: Average Hamiltonian Theory
date: 2024-02-15
authors:
  - name: Akinori Machino
---

# 平均ハミルトニアン理論

時間に依存しないハミルトニアン $H_0$ の時間発展演算子 $U_0(t)$ は、シュレーディンガー方程式

$$
\frac{d}{dt} U_0(t) = -i H_0 U_0(t)
$$

により

$$
U_0(t) = e^{-i H_0 t}
$$

で与えられるが、時間に依存するハミルトニアン $H(t)$ の場合、

$$
\frac{d}{dt} U(t) = -i H(t) U(t)
$$

は一般に解けず、ダイソン級数

$$
U(t) = I + \sum_{n=0}^\infty (-i)^n \int_0^t dt_1 \int_0^{t_1} dt_2 \cdots \int_0^{t_{n-1}} dt_n H(t_1) H(t_2) \cdots H(t_n)
$$

を考える必要があるのであった。

## マグナス展開 (Magnus expansion)

ダイソン級数を有限の項で打ち切ると、時間発展演算子 $U(t)$ のユニタリ性が保証されないという問題がある。これは、量子ゲートとしての $U(t)$ を考える場合などに都合が悪い。

そこで、 $U(t)$ のユニタリ性を保ったまま級数展開する方法として、マグナス展開を用いる。マグナス展開は、線形微分方程式の解の指数関数表現を与えてくれる数学的手法である。

今、解きたい線形微分方程式は、 $A(t) \equiv -i H(t)$ として

$$
\frac{d}{dt} U(t) = A(t) U(t)
$$

の格好をしている。

マグナス展開を用いると、この微分方程式の解は

$$
U(t) = e^{\Omega(t)}
$$

の形で、以下のように級数展開できることが知られている[^1]。

[^1]: https://en.wikipedia.org/wiki/Magnus_expansion

$$
\Omega(t) = \sum_{n=1}^\infty \Omega_n(t)
$$

$$
\begin{aligned}
\Omega_1(t) &=\int_0^t A(t_1) d t_1
\\
\Omega_2(t) &=\frac{1}{2} \int_0^t d t_1 \int_0^{t_1} d t_2\left[A(t_1), A(t_2)\right]
\\
\Omega_3(t) &= \frac{1}{6} \int_0^t d t_1 \int_0^{t_1} d t_2 \int_0^{t_2} d t_3\left(\left[A(t_1),\left[A(t_2), A(t_3)\right]\right]+\left[A(t_3),\left[A(t_2), A(t_1)\right]\right]\right)
\\
\Omega_4(t) &= \frac{1}{12} \int_0^t d t_1 \int_0^{t_1} d t_2 \int_0^{t_2} d t_3 \int_0^{t_3} d t_4\left(\left[\left[\left[A_1, A_2\right], A_3\right], A_4\right] \right.
\\
&\left.+ \left[A_1,\left[\left[A_2, A_3\right], A_4\right]\right]+\left[A_1,\left[A_2,\left[A_3, A_4\right]\right]\right]+\left[A_2,\left[A_3,\left[A_4, A_1\right]\right]\right]\right)
\end{aligned}
$$

すなわち $U(t)$ は

$$
\begin{aligned}
U(t) &= e^{\Omega(t)}
\\
&= e^{\Omega_1(t) + \Omega_2(t) + \Omega_3(t) + \cdots}
\end{aligned}
$$

で与えられる。

これを有限の項で打ち切ることで、ユニタリ性を保ったまま、時間発展演算子 $U(t)$ を近似的に求めることができる。

以下、マグナス級数を $n$ 次で打ち切った場合の時間発展演算子を $U^{(n)}(t)$ と書くことにする。

### 1次の平均ハミルトニアン

1次のマグナス展開は

$$
\begin{aligned}
\Omega_1(t) &= \int_0^t A(t_1) d t_1
\\
&= -i \int_0^t H(t_1) d t_1
\end{aligned}
$$

で与えられる。これを用いて

$$
\begin{aligned}
U^{(1)}(t) &= e^{\Omega_1(t)}
\\
&= e^{-i \int_0^t H(t_1) d t_1}
\end{aligned}
$$

となる。

ここで、「平均ハミルトニアン」 $\bar{H}$ を

$$
\begin{aligned}
\bar{H} &\equiv \frac{1}{t} \int_0^t H(t_1) d t_1
\end{aligned}
$$

と定義すると、 $U^{(1)}(t)$ は

$$
\begin{aligned}
U^{(1)}(t) &= e^{-i \bar{H} t}
\end{aligned}
$$

と書くことができる。

すなわち、1次のマグナス展開は、時間に依存する $H(t)$ の代わりに、 $H(t)$ を単純に時間平均した $\bar{H}$ を用いて物理系を近似することに対応する。これが、平均ハミルトニアン理論の名前の由来である。

以下、 $n$ 次の平均ハミルトニアン $\bar{H}^{(n)}$ を

$$
U^{(n)}(t) = e^{-i \bar{H}^{(n)} t}
$$

によって表されるものとして定義する。つまり

$$
\begin{aligned}
\bar{H}^{(n)} &= \frac{i}{t} \sum_{k=1}^n \Omega_k(t)
\end{aligned}
$$

である。

1次の平均ハミルトニアンは、前述の通り

$$
\begin{aligned}
\bar{H}^{(1)} &= \frac{1}{t} \int_0^t H(t_1) d t_1
\end{aligned}
$$

である。

### 2次の平均ハミルトニアン

$$
\begin{aligned}
\Omega_2(t) &= \frac{1}{2} \int_0^t d t_1 \int_0^{t_1} d t_2\left[A(t_1), A(t_2)\right]
\\
&= - \frac{1}{2} \int_0^t d t_1 \int_0^{t_1} d t_2\left[H(t_1), H(t_2)\right]
\end{aligned}
$$

より、2次の平均ハミルトニアンは

$$
\begin{aligned}
\bar{H}^{(2)} &= \frac{i}{t} \left( \Omega_1(t) + \Omega_2(t) \right)
\\
&= \frac{1}{t} \left( \int_0^t H(t_1) d t_1 - \frac{i}{2} \int_0^t d t_1 \int_0^{t_1} d t_2\left[H(t_1), H(t_2)\right] \right)
\\
&= \frac{1}{t} \left[ \int_0^t d t_1 \left( H(t_1) - \frac{i}{2} \int_0^{t_1} d t_2\left[H(t_1), H(t_2)\right] \right) \right]
\end{aligned}
$$

であり、時間発展演算子は

$$
\begin{aligned}
U^{(2)}(t) &= e^{-i \bar{H}^{(2)} t}
\\
&= \exp \left[ -i \left\{ \int_0^t d t_1 \left( H(t_1) - \frac{i}{2} \int_0^{t_1} d t_2\left[H(t_1), H(t_2)\right] \right) \right\} \right]
\end{aligned}
$$

となる。

### 3次の平均ハミルトニアン

$$
\begin{aligned}
\Omega_3(t) &= \frac{1}{6} \int_0^t d t_1 \int_0^{t_1} d t_2 \int_0^{t_2} d t_3\left(\left[A(t_1),\left[A(t_2), A(t_3)\right]\right]+\left[A(t_3),\left[A(t_2), A(t_1)\right]\right]\right)
\\
&= \frac{i}{6} \int_0^t d t_1 \int_0^{t_1} d t_2 \int_0^{t_2} d t_3\left(\left[H(t_1),\left[H(t_2), H(t_3)\right]\right]+\left[H(t_3),\left[H(t_2), H(t_1)\right]\right]\right)
\end{aligned}
$$

より、3次の平均ハミルトニアンは

$$
\begin{aligned}
\bar{H}^{(3)} &= \frac{i}{t} \left( \Omega_1(t) + \Omega_2(t) + \Omega_3(t) \right)
\\
&= \frac{1}{t} \left( \int_0^t H(t_1) d t_1 - \frac{i}{2} \int_0^t d t_1 \int_0^{t_1} d t_2\left[H(t_1), H(t_2)\right] - \frac{1}{6} \int_0^t d t_1 \int_0^{t_1} d t_2 \int_0^{t_2} d t_3\left(\left[H(t_1),\left[H(t_2), H(t_3)\right]\right]+\left[H(t_3),\left[H(t_2), H(t_1)\right]\right]\right) \right)
\\
&= \frac{1}{t} \left[ \int_0^t d t_1 \left( H(t_1) - \frac{i}{2} \int_0^{t_1} d t_2\left[H(t_1), H(t_2)\right] - \frac{1}{6} \int_0^{t_1} d t_2 \int_0^{t_2} d t_3\left(\left[H(t_1),\left[H(t_2), H(t_3)\right]\right]+\left[H(t_3),\left[H(t_2), H(t_1)\right]\right]\right) \right) \right]
\end{aligned}
$$

であり、時間発展演算子は

$$
\begin{aligned}
U^{(3)}(t) &= e^{-i \bar{H}^{(3)} t}
\\
&= \exp \left[ -i \left\{ \int_0^t d t_1 \left( H(t_1) - \frac{i}{2} \int_0^{t_1} d t_2\left[H(t_1), H(t_2)\right] - \frac{1}{6} \int_0^{t_1} d t_2 \int_0^{t_2} d t_3\left(\left[H(t_1),\left[H(t_2), H(t_3)\right]\right]+\left[H(t_3),\left[H(t_2), H(t_1)\right]\right]\right) \right) \right\} \right]
\end{aligned}
$$

となる。

## ユニタリ性の保証

2つのエルミート演算子 $A$ と $B$ に対して、その交換子 $[A, B]$ のエルミート共役は $[A, B]^\dagger = -[A, B]$ である。

この関係を用いると、平均ハミルトニアン $\bar{H}^{(n)}$ はすべてエルミート演算子であることが確認できる [^2]。

[^2]: はずである。一般に何故成り立つかはよく分かっていない。

したがって、マグナス展開をどの次数で打ち切ったとしても、 $U^{(n)}(t)$ がユニタリであることが保証されている。