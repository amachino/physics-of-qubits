## シュレーディンガー表示とハイゼンベルク表示

状態ベクトル

$$
\begin{aligned}
\ket{\psi} &= a \ket{0} + b \ket{1} \\
&\equiv \begin{pmatrix} a \\ b \end{pmatrix}
\end{aligned}
$$

の成分 $a,b$ が、ユニタリ行列 $U$ によって

$$
\begin{aligned}
\begin{pmatrix} a \\ b \end{pmatrix} \xrightarrow{U} \begin{pmatrix} a' \\ b' \end{pmatrix}
\end{aligned}
$$

と変化したとする。

例えば、 $U = \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix}$ であれば、

$$
\begin{aligned}
\begin{pmatrix} a' \\ b' \end{pmatrix}
&= U \begin{pmatrix} a \\ b \end{pmatrix}
\\
&= \begin{pmatrix} 0 & -1 \\ 1 & 0 \end{pmatrix} \begin{pmatrix} a \\ b \end{pmatrix}
\\
&= \begin{pmatrix} -b \\ a \end{pmatrix}
\end{aligned}
$$

である。

この状況には、2通りの解釈ができる。

1. 状態が変化し、 $\ket{\psi} \rightarrow \ket{\psi'} = U \ket{\psi}$ になった。基底は変わっていない。

$$
\begin{aligned}
\ket{\psi'}
&= U \ket{\psi}
\\
&= U \left( a \ket{0} + b \ket{1} \right)
\\
&= a' \ket{0} + b' \ket{1}
\\
&\equiv
\begin{pmatrix} a' \\ b' \end{pmatrix}
\end{aligned}
$$

2. 基底が変化し、 $\ket{n} \rightarrow \ket{n'} = U^\dagger \ket{n}$ になった。状態は変わっていない。

$$
\begin{aligned}
\ket{\psi'}
&= \ket{\psi}
\\
&= U U^\dagger \ket{\psi}
\\
&= U \left\{ a (U^\dagger \ket{0}) + b (U^\dagger \ket{1}) \right\}
\\
&= U \left( a \ket{0'} + b \ket{1'} \right)
\\
&= a' \ket{0'} + b' \ket{1'}
\\
&\equiv
\begin{pmatrix} a' \\ b' \end{pmatrix}
\end{aligned}
$$

前者がシュレーディンガー描像、後者がハイゼンベルク描像である。

よくある誤解に、ハイゼンベルク描像では $\ket{\psi}$ が変化しないので $\ket{\psi} = \begin{pmatrix} a \\ b \end{pmatrix}$ の成分も変わらない、というものがあるが、それは誤りである。ハイゼンベルク描像では状態ベクトル自体は変化しないが、その成分を決める基底が変化する。

成分の内積表示でも見てみよう。

1. 状態が変化し、 $\ket{\psi} \rightarrow \ket{\psi'} = U \ket{\psi}$ になった。基底は変わっていない。

$$
\begin{aligned}
\langle n | \psi' \rangle
&= \langle n | U \psi \rangle
\\
&= \bra{n} U \ket{\psi}
\end{aligned}
$$

2. 基底が変化し、 $\ket{n} \rightarrow \ket{n'} = U^\dagger \ket{n}$ になった。状態は変わっていない。

$$
\begin{aligned}
\langle n' | \psi \rangle
&= \langle U^\dagger n | \psi \rangle
\\
&= \bra{n} U \ket{\psi}
\end{aligned}
$$

となり、どちらの描像でも一致する。

観測量 $\langle A \rangle \xrightarrow{U} \langle A' \rangle$ についても、それぞれの描像でみてみよう。

1. 状態が変化し、 $\ket{\psi} \rightarrow \ket{\psi'} = U \ket{\psi}$ になった。 $A$ は変わっていない。

$$
\begin{aligned}
\langle A' \rangle &=
\bra{\psi'}A\ket{\psi'}
\\
&= \langle U \psi | A | U \psi \rangle
\\
&= \bra{\psi}U^\dagger A U\ket{\psi}
\end{aligned}
$$

2. $A$ が変化し、 $A \rightarrow A' = U^\dagger A U$ になった。状態は変わっていない。

$$
\begin{aligned}
\langle A' \rangle &=
\bra{\psi}A'\ket{\psi}
\\
&= \bra{\psi}U^\dagger A U\ket{\psi}
 \end{aligned}
$$

となり、確かに同じになる。

$U^\dagger A U = A$ を満たす $A$ は、 $\langle A' \rangle = \langle A \rangle$ となり、ユニタリ変換 $U$ によって不変である。

また、

$$
\begin{aligned}
U^\dagger A U &= A \\
AU &= UA \\
[A, U] &= 0
\end{aligned}
$$

なので、 $U^\dagger A U = A$ という条件は、 $A$ と $U$ が可換であることと等しい。

例えば、$U = \sigma_z$ というユニタリ変換に対して、 $S_z = \frac{\hbar}{2} \sigma_z$ は可換であるため $\langle S_z \rangle$ は不変だが、 $S_x = \frac{\hbar}{2} \sigma_x$ は可換でないので $\langle S_x \rangle$ は変化する。


## 相互作用表示

### 回転座標系

時間に依存しないハミルトニアン $H_0$ によって、状態 $\ket{\psi}$ は

$$
\begin{aligned}
\ket{\psi'}
&= e^{-i H_0 t} \ket{\psi}
\end{aligned}
$$

のように時間発展する。

これは状態ベクトルが変化し、基底は変化しないシュレーディンガー表示である。

ここから、基底も同じ $e^{-i H_0 t}$ によって

$$
\begin{aligned}
\ket{n} \rightarrow \ket{n'} = e^{-i H_0 t} \ket{n}
\end{aligned}
$$

と変化する座標系を考えよう。

状態の変化に追随して基底も変化するので、状態ベクトルの成分は変化しない。

このとき、状態ベクトルの成分は

$$
\begin{aligned}
\langle n' | \psi' \rangle
&= \langle e^{-i H_0 t} n | e^{-i H_0 t} \psi \rangle
\\
&= \bra{n} e^{i H_0 t} e^{-i H_0 t} \ket{\psi}
\\
&= \langle n | \psi \rangle
\end{aligned}
$$

となり、変化しない。

ハミルトニアン $H$ はユニタリ変換 $U$ によって

$$
\begin{aligned}
H' &= U^\dagger H U -i U^\dagger \dot{U}
\end{aligned}
$$

で変換されるので、

$$
\begin{aligned}
H_0' &= e^{i H_0 t} H_0 e^{-i H_0 t} -i e^{i H_0 t} \frac{d}{dt} e^{-i H_0 t}
\\
&= H_0 - H_0
\\
&= 0
\end{aligned}
$$

となり、ハミルトニアンは 0 になる。

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

このとき、状態ベクトルは

$$
\begin{aligned}
i \frac{d}{dt} \ket{\psi} &= V'(t) \ket{\psi}
\\
&= e^{i H_0 t} V e^{-i H_0 t} \ket{\psi}
\end{aligned}
$$

に従って時間発展する。

これを、 $H_0$ の相互作用表示とも呼ぶ。


### パルス座標系

逆に、時間に依存するハミルトニアン $V$ の相互作用表示を考えよう。

ユニタリ行列 $U$ を

$$
\begin{aligned}
U_V &= \mathcal{T} \exp \left( -i \int_0^t V(t') dt' \right)
\end{aligned}
$$

として、状態ベクトルは

$$
\begin{aligned}
\ket{\psi'}
&= U_V \ket{\psi}
\end{aligned}
$$

で時間発展する。

全体のハミルトニアンが

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
