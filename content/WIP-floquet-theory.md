---
title: Floquet Theory
date: 2024-02-15
authors:
  - name: Akinori Machino
---

# フロケ理論 (Floquet Theory)

一定の時間周期 $T$ を持つハミルトニアン $H(t)$ を考えよう。

$$
H(t) = H(t + T)
$$

## フロケの定理

フロケ理論によれば、線形微分方程式

$$
\dot{x} = A(t) x
$$

の $A(t)$ が周期 $T$ を持つとき、その解は次のような積の形で表される。

$$
x(t) = P(t) e^{t \Lambda}
$$

ここで、$P(t)$ は周期関数であり、$\Lambda$ は定数行列である。

## フロケハミルトニアン

フロケの定理を、シュレーディンガー方程式

$$
\frac{d}{dt} U(t) = - i H(t) U(t)
$$

に適用すると、時間発展演算子 $U(t)$ は次のように書ける。

$$
U(t) = P(t) e^{-i H_F t}
$$

ここで、 $P(t)$ は周期 $T$ を持つ演算子、$H_F$ は時間に依存しない演算子である。初期条件を $U(0) = I$ とすれば、 $P(0) = I$ である。

この $H_F$ を1周期分の適用させた時間発展演算子を

$$
U_F = e^{-i H_F T}
$$

とすると、 $t = n T$ における時間発展は

$$
U(n T) = e^{-i H_F n T}
$$

と記述できる。

これは、この系を周期 $T$ でストロボスコピック（ $t= 0, T, 2T, \cdots$ ）に観測するとき、その時間発展は $H_F$ によって完全に記述されることを意味する。

$H_F$ はフロケハミルトニアン、$U_F$ はフロケ演算子と呼ばれる。

### フロケハミルトニアンの関係式

$$
U(t) = P(t) e^{-i H_F t}
$$

を

$$
\frac{d}{dt} U(t) = - i H(t) U(t)
$$

に代入すると、

$$
\begin{aligned}
\frac{d}{dt} \left(P(t) e^{-i H_F t}\right) &= - i H(t) P(t) e^{-i H_F t} \\
\frac{d}{dt} P(t) e^{-i H_F t} -i H_F P(t) e^{-i H_F t} &= - i H(t) P(t) e^{-i H_F t} \\
\frac{d}{dt} P(t) &= -i P(t) H(t) + i H_F P(t)
\end{aligned}
$$

の関係式が得られる。
