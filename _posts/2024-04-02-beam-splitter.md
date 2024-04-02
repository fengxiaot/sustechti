---
title: 分束器的量子理论
image: assets/img/2024-04-02-beam-splitter.jpg
author: xiaotian-feng
tags: quantum optics
---

<!-- excerpt start -->
A beam splitter is an optical device that splits a beam of light into a transmitted and a reflected beam. It is a crucial part of many optical experimental and measurement systems, such as interferometers, also finding widespread application in fibre optic telecommunications. 
<!-- excerpt end -->

## Beam Splitter

### Transfer matrix

The recipe for quantization is that 'replace the classical amplitudes by annihilation operators'. Namely,
$$
\begin{bmatrix}
b_1 \\
b_2
\end{bmatrix}
=
\begin{bmatrix}
t & r^\prime\\
r & t^\prime
\end{bmatrix}
\begin{bmatrix}
a_1 \\
a_2
\end{bmatrix}
$$
which means
$$
\begin{gathered}
b_1 = t a_1 + r^\prime a_2 \qquad b_2 = r a_1 + t^\prime a_2 \\
b_1^\dagger =t^* a_1^\dagger+r^{\prime*} a_2^\dagger \qquad b_2^\dagger = r^* a_1^\dagger + t^{\prime *} a_2^\dagger
\end{gathered}
$$
If the outgoing modes are still useful for the quantum theory, they have to satisfy the commutation relations
$$
[b_i,b_j^\dagger] = \delta_{ij}
$$
which is identical to
$$
\begin{cases}
t r^* + r^\prime t^{\prime*} = 0 \\
|t|^2+|r^\prime|^2 =1 \\
|r|^2+|t^\prime|^2=1
\end{cases}
$$
which is also identical to
$$
U = \begin{bmatrix}
t & r^\prime\\
r & t^\prime
\end{bmatrix} \text{ is unitary.}
$$
Since $U\in\mathrm{SU}(2)$, the transfer matrix could be written as $U = \exp\left[-\frac{\mathrm{i}}{2} \theta\,(\boldsymbol{n} \cdot \boldsymbol{\sigma})\right]$. The most common form of $U$, however, is
$$
U= \begin{bmatrix}
\cos\theta & \sin\theta \mathrm{e}^\mathrm{i \phi} \\
-\sin\theta \mathrm{e}^\mathrm{-i \phi} & \cos\theta
\end{bmatrix}
$$
Inversely, we have
$$
\begin{bmatrix}
b_1 \\
b_2
\end{bmatrix}
=
U
\begin{bmatrix}
a_1 \\
a_2
\end{bmatrix}
\qquad
\begin{bmatrix}
a_1 \\
a_2
\end{bmatrix}
=
U^\dagger
\begin{bmatrix}
b_1 \\
b_2
\end{bmatrix}
$$
and
$$
\begin{gathered}
a_1^\dagger = b_1^\dagger \cos\theta -b_2^\dagger \sin\theta \mathrm{e}^{-\mathrm{i}\phi} \\
a_2^\dagger = b_1^\dagger \sin\theta \mathrm{e}^{\mathrm{i}\phi} + b_2^\dagger \cos\theta
\end{gathered}
$$

### Beam splitter operator

#### State Space

For fibre optics (i.e. waveguide beam splitter), we can pair two input ports with two output ports.[^1] This correspondence does not imply that a photon on an input port is identical to a photon on an output port (e.g. $\ket{10}_\text{in} \neq \ket{10}_\text{out}$). Rather, the photon number states in the upper and lower fibers, no matter they belong to input or output, can be considered to be in the same state space, and the beam splitter actually acts as a transformation in this state space. 

For example, a 50:50 beam splitter acting on a single-photon incident state should be strictly written as
$$
BS(\pi/4) \,(\ket{10}_\text{in} \otimes \ket{00}_\text{out}) = \ket{00}_\text{in} \otimes\frac{1}{\sqrt{2}}(\ket{10}_\text{out}+\ket{01}_\text{out})
$$
However, if we focus only on the photon number, we can write
$$
BS(\pi/4) \ket{10}= \frac{1}{\sqrt{2}}(\ket{10}-\ket{01})
$$
where the first number in the ket represents the photon number in the upper fibre, and the second number represents the photon number in the lower fibre. And, we recognize by default, that the state before BS operators acting on them represents the photon distribution in the input fibers while the state transformed represents the photon distribution in the output fibers.

This can also be glimpsed in the creation and annihilation operators. The linear relationship between $b,b^\dagger$ and $a,a^\dagger$ suggests that they can be considered to act on the same state space.

> Example: Hong–Ou–Mandel interference
>
> Answer: Let us consider two single-photon states incident on the same beam splitter $\ket{11}_\text{in}$.
> $$
> \begin{aligned}
> \ket{11}_\text{in} &= a_1^\dagger a_2^\dagger \ket{00}_\text{in}= a_1^\dagger a_2^\dagger \ket{00}_\text{out} = (b_1^\dagger\cos\theta - b_2^\dagger\sin\theta)(b_1^\dagger\sin\theta + b_2^\dagger\cos\theta) \ket{00}_\text{out} \\
> &= \sqrt{2}\sin\theta\cos\theta(\ket{20}_\text{out}-\ket{02}_\text{out}) +\cos(2\theta)\ket{11}_\text{out}
> \end{aligned}
> $$
> When the beam splitter is 50:50, the output is $\frac{1}{\sqrt{2}} (\ket{20}-\ket{02})$, which means the photons are either in the upper or in the lower fibre!

Overall, beam splitter operator $BS$ has the following properties:

1. Each $BS$ operator associates with a transfer matrix $U$
2. $BS$ does not change the total photon number of incident beam
3. $BS \in SU(2)$ 
4. $BS \ket{n_1,n_2} = \sum_m\ket{lm}$, where $l=n_1+n_2$ and $m=|n_1-n_2|,\cdots,|n_1+n_2|$.

#### Schwinger representation

The angular momentum operator can be expressed by two independent harmonic oscillators.
$$
L_x =\frac{1}{2}(a_1^\dagger a_2+a_1 a_2^\dagger) \qquad L_y =\frac{1}{2\mathrm{i}}(a_1^\dagger a_2 - a_1 a_2^\dagger) \qquad L_z=\frac{1}{2}(a_1^\dagger a_1 -a_2^\dagger a_2)
$$

$$
L_+ = L_x + \mathrm{i} L_y = a_1^\dagger a_2 \qquad L_-= L_x - \mathrm{i} L_y = a_1 a_2^\dagger
$$

$$
L^2= \hat{l}(\hat{l}+1) \qquad \hat{l} =\frac{1}{2}(\hat{n}_1 + \hat{n}_2)=\frac{1}{2} (a_1^\dagger a_1 +a_2^\dagger a_2)
$$

It is easy to check such angular momentum operators satisfying the commutation rules $[L_i,L_j] = \mathrm{i}\varepsilon_{ijk} L_k$. Therefore, the most general form of $BS$ could be written as
$$
BS =\exp\left[\mathrm{i} (\alpha L_x + \beta L_y + \gamma L_z)\right]
$$

#### Relationship

The relationship between the beam splitter operators $BS$ acting on the states and the transfer matrix $U$ acting on the creation and annihilation operators is[^2]
$$
U= \begin{bmatrix}
\cos\theta & \sin\theta \mathrm{e}^\mathrm{i \phi} \\
-\sin\theta \mathrm{e}^\mathrm{-i \phi} & \cos\theta
\end{bmatrix}
\iff BS= \mathrm{e}^{\xi L_+ -\xi^*L_-} = \exp\left[\theta(\mathrm{e}^\mathrm{i \phi} a_1^\dagger a_2-\mathrm{e}^\mathrm{-i \phi} a_1 a_2^\dagger)\right]
$$

with
$$
\begin{gathered}
BS^\dagger a_1 BS= a_1 \cos\theta +a_2 \mathrm{e}^{\mathrm{i}\phi}\sin\theta =b_1\\
BS^\dagger a_2 BS= -a_1 \mathrm{e}^{-\mathrm{i}\phi}\sin\theta +a_2 \cos\theta  =b_2
\end{gathered}
$$

Here is a short Python code to check the relations

```python
import qutip as qt
import numpy as np

dim1 = 10
a1 = qt.destroy(dim1)
a1_dag = qt.create(dim1)
I1 = qt.qeye(dim1)

dim2 = 10
a2 = qt.destroy(dim2)
a2_dag = qt.create(dim2)
I2 = qt.qeye(dim2)

a1 = qt.tensor(a1,I2)
a1_dag = qt.tensor(a1_dag,I2)
a2 = qt.tensor(I1,a2)
a2_dag = qt.tensor(I1,a2_dag)

# Hong–Ou–Mandel interference
n1 = 1
n2 = 1
theta = np.pi/4
phi = np.pi/2

input = qt.tensor(qt.basis(dim1,n1),qt.basis(dim2,n2))
vac = qt.tensor(qt.basis(dim1,0),qt.basis(dim2,0))
out1_dag = a1_dag*np.cos(theta) - a2_dag*np.sin(theta)*np.exp(-1j*phi)
out2_dag = a1_dag*np.sin(theta)*np.exp(1j*phi) + a2_dag*np.cos(theta)
bs = (theta*(a1_dag*a2*np.exp(1j*phi)-a1*a2_dag*np.exp(-1j*phi))).expm()
output1 = bs*input
output2 = 1/np.sqrt(np.math.factorial(n1)*np.math.factorial(n2))*out1_dag**n1*out2_dag**n2*vac

print(qt.fidelity(output1,output2))
```



[^1]: Makarov D. Theory for the beam  splitter in quantum optics: Quantum entanglement of photons and their  statistics, HOM effect[J]. Mathematics, 2022, 10(24): 4794.
[^2]: Campos R A, Saleh B E A, Teich M C.  Quantum-mechanical lossless beam splitter: SU (2) symmetry and photon  statistics[J]. Physical Review A, 1989, 40(3): 1371.

