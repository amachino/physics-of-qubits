---
title: Lattice transmon Hamiltonian
date: 2023-02-02
authors:
  - name: Akinori Machino
---

# トランズモン結合系のハミルトニアン

自由ハミルトニアンが $H_1, H_2$ で表わされる2つのトランズモンが結合定数 $g_{12}$ で相互作用するときのハミルトニアンは、

$$
\begin{aligned}
H_1 &= \omega_1 b_1^\dagger b_1 + \frac{\alpha_1}{2} b_1^{\dagger 2} b_1^2
\\
H_2 &= \omega_2 b_2^\dagger b_2 + \frac{\alpha_2}{2} b_2^{\dagger 2} b_2^2
\\
H_{12} &= g_{12} \left( b_1^\dagger + b_1 \right) \left( b_2^\dagger + b_2 \right)
\end{aligned}
$$

として、

$$
\begin{aligned}
H &= H_1 + H_2 + H_{12}
\end{aligned}
$$

と表わされる。


## 格子状に結合したトランズモンのハミルトニアン

トランズモンを格子状に結合した系のハミルトニアンは、

$$
\begin{aligned}
H_i &= \omega_i b_i^\dagger b_i + \frac{\alpha_i}{2} b_i^{\dagger 2} b_i^2
\\
H_{ij} &= g_{ij} \left( b_i^\dagger + b_i \right) \left( b_j^\dagger + b_j \right)
\end{aligned}
$$

として、

$$
\begin{aligned}
H &= \sum_i H_i + \sum_{\langle i, j \rangle} H_{ij}
\end{aligned}
$$

と表わされる。ここで、$\langle i, j \rangle$ は隣接する格子点を表わす。

### 2x2 格子の場合

$$
\begin{matrix}
\boxed{H_0} &\cdots& g_{01} &\cdots& \boxed{H_1} \\
\vdots && && \vdots \\
g_{02} && && g_{13} \\
\vdots && && \vdots \\
\boxed{H_2} &\cdots& g_{23} &\cdots& \boxed{H_3}
\end{matrix}
$$

のような2x2格子の場合、$H$ は

$$
\begin{aligned}
H &= H_0 + H_1 + H_2 + H_3 \\
&+ g_{01} \left( b_0^\dagger + b_0 \right) \left( b_1^\dagger + b_1 \right) \\
&+ g_{02} \left( b_0^\dagger + b_0 \right) \left( b_2^\dagger + b_2 \right) \\
&+ g_{13} \left( b_1^\dagger + b_1 \right) \left( b_3^\dagger + b_3 \right) \\
&+ g_{23} \left( b_2^\dagger + b_2 \right) \left( b_3^\dagger + b_3 \right)
\end{aligned}
$$

と表わされる。

ここで、ユニタリ変換

$$
\begin{aligned}
U &= e^{-i \omega_0 b_0^\dagger b_0 t}
e^{-i \omega_1 b_1^\dagger b_1 t}
e^{-i \omega_2 b_2^\dagger b_2 t}
e^{-i \omega_3 b_3^\dagger b_3 t} \\
\end{aligned}
$$

によって全てのトランズモンの回転座標系に乗れば、回転波近似を適用して、

$$
\begin{aligned}
H'
&= U^\dagger H U -i U^\dagger \dot{U}
\\
&= \sum_{i}\frac{\alpha_i}{2} b_i^{\dagger 2} b_i^2
+ \sum_{\langle i, j \rangle} g_{ij} \left\{ b_i^\dagger b_j e^{i (\omega_i - \omega_j) t}
+ b_i b_j^\dagger e^{-i (\omega_i - \omega_j) t} \right\}
\end{aligned}
$$

とできる。

このとき、 $H'$ の基底は

$$
\begin{aligned}
\ket{n_0 n_1 n_2 n_3}' &= U^\dagger \ket{n_0 n_1 n_2 n_3}
\\
&= e^{i \left(\omega_0 b^\dag b_0 + \omega_1 b^\dag b_1 + \omega_2 b^\dag b_2 + \omega_3 b^\dag b_3 \right) t} \ket{n_0 n_1 n_2 n_3}
\\
&= e^{i \left(n_0 \omega_0 + n_1 \omega_1 + n_2 \omega_2 + n_3 \omega_3 \right) t} \ket{n_0 n_1 n_2 n_3}
\end{aligned}
$$

と変換されており、各トランズモンの基底も、

$$
\begin{aligned}
\ket{n}'_i 
&= e^{i \omega_i b^\dag b_i t} \ket{n}_i
\\
&= e^{i n_i \omega_i t} \ket{n}_i
\end{aligned}
$$

と変換されている。