---
title: Coupled Transmon Hamiltonian
date: 2023-09-13
authors:
  - name: Akinori Machino
---

# トランズモン結合系のハミルトニアン

自由ハミルトニアンが $H_1, H_2$ で表わされる2つのトランズモンが結合定数 $g$ で相互作用するときのハミルトニアンは、

$$
\begin{aligned}
H_1 &= \omega_1 b_1^\dagger b_1 + \frac{\alpha_1}{2} b_1^{\dagger 2} b_1^2
\\
H_2 &= \omega_2 b_2^\dagger b_2 + \frac{\alpha_2}{2} b_2^{\dagger 2} b_2^2
\\
V &= g \left( b_1^\dagger + b_1 \right) \left( b_2^\dagger + b_2 \right)
\end{aligned}
$$

として、

$$
\begin{aligned}
H &= H_1 + H_2 + V
\end{aligned}
$$

と表わされる。

ここで、ユニタリ変換

$$
U = e^{-i \omega_1 b_1^\dagger b_1 t}
e^{-i \omega_2 b_2^\dagger b_2 t}
$$

によって基底変換し、

$$
H' = U^\dagger H U -i U^\dagger \dot{U}
$$

を考えよう。

$H$ の基底を $\ket{n_1 n_2} = \ket{n}_1 \otimes \ket{n}_2$ とすれば、$H'$ の基底は

$$
\begin{aligned}
\ket{n_1 n_2}' &= U^\dagger \ket{n_1 n_2}
\\
&= e^{i \omega_1 b_1^\dagger b_1 t} \ket{n}_1 \otimes e^{i \omega_2 b_2^\dagger b_2 t} \ket{n}_2
\\
&= e^{i n_1 \omega_1 t} \ket{n}_1 \otimes e^{i n_2 \omega_2 t} \ket{n}_2
\\
&= e^{i (n_1 \omega_1 + n_2 \omega_2) t} \ket{n_1 n_2}
\end{aligned}
$$

と変換される。また

$$
\begin{aligned}
\ket{n}'_1 &= e^{i n_1 \omega_1 t} \ket{n}_1 
\\
\ket{n}'_2 &= e^{i n_2 \omega_2 t} \ket{n}_2 
\end{aligned}
$$

として

$$
\begin{aligned}
\ket{n_1 n_2}' &= \ket{n}'_1 \otimes \ket{n}'_2
\end{aligned}
$$

となる。

このとき、

$$
\begin{aligned}
U^\dagger \dot{U}
&= e^{i \left( \omega_1 b_1^\dagger b_1 + \omega_2 b_2^\dagger b_2 \right) t}
\frac{d}{dt} \left( e^{-i \left( \omega_1 b_1^\dagger b_1 + \omega_2 b_2^\dagger b_2 \right) t} \right)
\\
&= -i \left( \omega_1 b_1^\dagger b_1 + \omega_2 b_2^\dagger b_2 \right)
\end{aligned}
$$

であるから

$$
-i U^\dagger \dot{U} = - \omega_1 b_1^\dagger b_1 - \omega_2 b_2^\dagger b_2
$$

であり、

$$
\begin{aligned}
H_i &=
\omega_i b_i^\dagger b_i + \frac{\alpha_i}{2} b_i^{\dagger 2} b_i^2
\\
&=
\left(\omega_i - \frac{\alpha_i}{2} \right) b_i^\dagger b_i + \frac{\alpha_i}{2} (b_i^\dagger b_i)^2
\end{aligned}
$$

が $b_i^\dagger b_i$ と可換であることに注意すれば、

$$
\begin{aligned}
U^\dagger H_i U = H_i
\end{aligned}
$$

である。

残りの

$$
\begin{aligned}
V
&= g \left( b_1^\dagger + b_1 \right) \left( b_2^\dagger + b_2 \right)
\\
&= g \left( b_1^\dagger b_2^\dagger + b_1^\dagger b_2 + b_1 b_2^\dagger + b_1 b_2 \right)
\end{aligned}
$$

部分の変換 $U^\dagger V U$ を計算しよう。Baker–Campbell–Hausdorff 公式を使えば、

$$
\begin{aligned}
e^{i \omega_i b_i^\dagger b_i t} b_i e^{- i \omega_i b_i^\dagger b_i t} &= b_i e^{-i \omega_i t}
\\
e^{i \omega_i b_i^\dagger b_i t} b_i^\dagger e^{- i \omega_i b_i^\dagger b_i t} &= b_i^\dagger e^{i \omega_i t}
\end{aligned}
$$

になるので、

$$
\begin{aligned}
U^\dagger V U
&= g U^\dagger \left( b_1^\dagger b_2^\dagger + b_1^\dagger b_2 + b_1 b_2^\dagger + b_1 b_2 \right) U
\\
&= g \left( b_1^\dagger e^{i \omega_1 t} b_2^\dagger e^{i \omega_2 t}
+ b_1^\dagger e^{i \omega_1 t} b_2 e^{-i \omega_2 t}
+ b_1 e^{-i \omega_1 t} b_2^\dagger e^{i \omega_2 t}
+ b_1 e^{-i \omega_1 t} b_2 e^{-i \omega_2 t} \right)
\\
&= g \left( b_1^\dagger b_2^\dagger e^{i (\omega_1 + \omega_2) t}
+ b_1^\dagger b_2 e^{i (\omega_1 - \omega_2) t}
+ b_1 b_2^\dagger e^{-i (\omega_1 - \omega_2) t}
+ b_1 b_2 e^{-i (\omega_1 + \omega_2) t} \right)
\end{aligned}
$$

このとき、$\omega_1 + \omega_2$ で振動する第1項と第4項は、 $\omega_1 - \omega_2$ で振動する第2項と第3項に比べて振動数が十分に大きいので、時間平均を取ると消えてしまう。したがって、

$$
\begin{aligned}
U^\dagger V U
&\sim g \left( b_1^\dagger b_2 e^{i (\omega_1 - \omega_2) t}
+ b_1 b_2^\dagger e^{-i (\omega_1 - \omega_2) t} \right)
\\
\end{aligned}
$$

とできる。これを回転波近似 (Rotating Wave Approximation) という。

以上より、

$$
\begin{aligned}
H'
&= U^\dagger H U -i U^\dagger \dot{U}
\\
&= \omega_1 b_1^\dagger b_1 + \frac{\alpha_1}{2} b_1^{\dagger 2} b_1^2
+ \omega_2 b_2^\dagger b_2 + \frac{\alpha_2}{2} b_2^{\dagger 2} b_2^2 + g \left( b_1^\dagger b_2 e^{i (\omega_1 - \omega_2) t}
+ b_1 b_2^\dagger e^{-i (\omega_1 - \omega_2) t} \right)
- \omega_1 b_1^\dagger b_1 - \omega_2 b_2^\dagger b_2
\\
&= \frac{\alpha_1}{2} b_1^{\dagger 2} b_1^2
+ \frac{\alpha_2}{2} b_2^{\dagger 2} b_2^2 + g \left( b_1^\dagger b_2 e^{i (\omega_1 - \omega_2) t}
+ b_1 b_2^\dagger e^{-i (\omega_1 - \omega_2) t} \right)
\end{aligned}
$$

となる。

$$
U = e^{-i \omega_1 b_1^\dagger b_1 t}
e^{-i \omega_2 b_2^\dagger b_2 t}
$$

の代わりに

$$
U_1 = e^{-i \omega_1 b_1^\dagger b_1 t}
e^{-i \omega_1 b_2^\dagger b_2 t}
$$

で変換すると、

$$
\begin{aligned}
H''
&= U_1^\dagger H U_1 -i U_1^\dagger \dot{U_1}
\\
&= \omega_1 b_1^\dagger b_1 + \frac{\alpha_1}{2} b_1^{\dagger 2} b_1^2
+ \omega_2 b_2^\dagger b_2 + \frac{\alpha_2}{2} b_2^{\dagger 2} b_2^2 + g \left( b_1^\dagger b_2 e^{i (\omega_1 - \omega_1) t}
+ b_1 b_2^\dagger e^{-i (\omega_1 - \omega_1) t} \right)
- \omega_1 b_1^\dagger b_1 - \omega_1 b_2^\dagger b_2
\\
&= \frac{\alpha_1}{2} b_1^{\dagger 2} b_1^2
+ (\omega_2 - \omega_1) b_2^\dagger b_2
+ \frac{\alpha_2}{2} b_2^{\dagger 2} b_2^2 + g \left( b_1^\dagger b_2
+ b_1 b_2^\dagger \right)
\end{aligned}
$$

になる。これは、1つ目のトランズモンの回転座標系であり、基底は

$$
\begin{aligned}
\ket{n_1 n_2}'' &= U_1^\dagger \ket{n_1 n_2}
\\
&= e^{i \omega_1 b_1^\dagger b_1 t} \ket{n}_1 \otimes e^{i \omega_1 b_2^\dagger b_2 t} \ket{n}_2
\\
&= e^{i \omega_1 (n_1 + n_2) t} \ket{n_1 n_2}
\end{aligned}
$$

と変換される。また

$$
\begin{aligned}
\ket{n}''_1 &= e^{i n_1 \omega_1 t} \ket{n}_1 
= \ket{n}'_1
\\
\ket{n}''_2 &= e^{i n_2 \omega_1 t} \ket{n}_2 
= e^{i n_2 (\omega_1 - \omega_2) t} \ket{n}_2'
\end{aligned}
$$

である。

2番目のトランズモンの量子状態は

$$
\begin{aligned}
\ket{\psi}_2 &= \sum_{n} c_{n} \ket{n}''_2
\\
&= \sum_{n} c_{n} e^{i n (\omega_1 - \omega_2) t} \ket{n}_2'
\end{aligned}
$$

であるので、トランズモン 1 の回転座標系の状態ベクトルの係数に対して $e^{i n (\omega_1 - \omega_2) t}$ をかけることで、トランズモン 2 の回転座標系の係数を得ることができる。
