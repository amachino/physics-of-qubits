---
title: Interaction Picture
date: 2024-02-14
authors:
  - name: Akinori Machino
---

# 相互作用表示

## 回転座標系 (rotating frame)

時間に依存しないハミルトニアン $H_0$ を考える。このとき、量子状態 $\ket{\psi}$ は $U = e^{-i H_0 t}$ によって

$$
\begin{aligned}
\ket{\psi_t}
&= U \ket{\psi_0}
\\
&= e^{-i H_0 t} \ket{\psi_0}
\end{aligned}
$$

のように時間発展する。これは状態ベクトルが変化し、基底は変化しないシュレーディンガー表示である。

ここで、基底ベクトルも状態の時間発展と同じく $U = e^{-i H_0 t}$ で変化する新たな座標系を考えよう。

その基底で表される状態ベクトル $\ket{\psi_t}'$ は、

$$
\begin{aligned}
\ket{\psi_t}'
&= U^\dagger \ket{\psi_t}
\\
&= e^{i H_0 t} e^{-i H_0 t} \ket{\psi_0}
\\
&= \ket{\psi_0}
\end{aligned}
$$

となり、時間に依存しない。すなわち、この座標系においてハミルトニアンはゼロである。

実際、 $\ket{\psi_t}'= U^\dagger \ket{\psi_t}$ の関係式を時間で微分すると、

$$
\begin{aligned}
\frac{d}{dt} \ket{\psi_t}'
&= \frac{d}{dt} \left( U^\dagger \ket{\psi_t} \right)
\\
&= \dot{U}^\dagger \ket{\psi_t} + U^\dagger \frac{d}{dt} \ket{\psi_t}
\\
&= \dot{U}^\dagger \ket{\psi_t} - i U^\dagger H_0 \ket{\psi_t}
\\
&= -i \left( U^\dagger H_0 + i \dot{U}^\dagger \right) \ket{\psi_t}
\\
&= -i \left( U^\dagger H_0 U + i \dot{U}^\dagger U \right) \ket{\psi_t}'
\\
&= -i \left( U^\dagger H_0 U -i U^\dagger \dot{U} \right) \ket{\psi_t}'
\\
&\equiv -i H'_0 \ket{\psi_t}'
\end{aligned}
$$

であり、新たな座標系でのハミルトニアン $H'_0$ は

$$
\begin{aligned}
H'_0 &= U^\dagger H_0 U -i U^\dagger \dot{U}
\\
&= e^{i H_0 t} H_0 e^{-i H_0 t} -i e^{i H_0 t} \frac{d}{dt} e^{-i H_0 t}
\\
&= H_0 -i (-i H_0)
\\
&= H_0 - H_0
\\
&= 0
\end{aligned}
$$

と、確かにゼロになることが確認できる。

この座標系を $H_0$ の回転座標系と呼ぼう。この座標系では、 $H_0$ の物理系は静止しているように見える。

この $H_0$ の回転座標系で、全体のハミルトニアンが

$$
\begin{aligned}
H &= H_0 + V
\end{aligned}
$$

で表わされる状況を考えよう。

このとき、 $H_0$ の回転座標系での $H'$ は

$$
\begin{aligned}
H' &= U^\dagger H U -i U^\dagger \dot{U}
\\
&= U^\dagger (H_0 + V) U -i U^\dagger \dot{U}
\\
&= U^\dagger H_0 U + U^\dagger V U -i U^\dagger \dot{U}
\\
&= U^\dagger V U
\\
&= e^{i H_0 t} V e^{-i H_0 t}
\\
&\equiv V'
\end{aligned}
$$

となる。

したがって、$H_0$ の回転座標系における $H$ のシュレーディンガー方程式は

$$
\begin{aligned}
i \frac{d}{dt} \ket{\psi}' &= V' \ket{\psi}'
\\
&= e^{i H_0 t} V e^{-i H_0 t} \ket{\psi}'
\end{aligned}
$$

である。これを、 $H_0$ の相互作用表示とも呼ぶ。


## 駆動座標系 (toggling frame)

逆に、時間に依存するハミルトニアン $V(t)$ の相互作用表示を考えよう。

$V(t)$ による時間発展演算子を

$$
\begin{aligned}
U_V &= \mathcal{T} \exp \left( -i \int_0^t V(t') dt' \right)
\end{aligned}
$$

として、全体のハミルトニアンが

$$
\begin{aligned}
H &= H_0 + V
\end{aligned}
$$

のとき、 $V$ の相互作用表示 $H'$ は

$$
\begin{aligned}
H' &= U_V^\dagger H U_V -i U_V^\dagger \dot{U}_V
\\
&= U_V^\dagger (H_0 + V) U_V -i U_V^\dagger \dot{U}_V
\\
&= U_V^\dagger H_0 U_V + U_V^\dagger V U_V -i U_V^\dagger \dot{U}_V
\\
&= U_V^\dagger H_0 U_V 
\end{aligned}
$$

となる。

最後の等式では、ユニタリ行列のシュレーディンガー方程式

$$
\begin{aligned}
i \frac{d}{dt} U_V &= V U_V
\end{aligned}
$$

に左から $U_V^\dagger$ をかけて得られる

$$
\begin{aligned}
i U_V^\dagger \dot{U_V} &= U_V^\dagger V U_V
\end{aligned}
$$

を使った。 