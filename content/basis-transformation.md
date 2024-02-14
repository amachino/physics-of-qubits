---
title: Basis Transformation
date: 2023-09-28
authors:
  - name: Akinori Machino
---

# 基底変換

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