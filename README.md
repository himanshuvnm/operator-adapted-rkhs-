# Operator-Adapted Reproducing Kernel Geometries

[![NeurIPS 2026](https://img.shields.io/badge/NeurIPS%202026-GlobalSouthAI-blue)]()
[![Python](https://img.shields.io/badge/Python-3.12+-blue)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)]()

Official repository accompanying:

## Operator-Adapted Reproducing Kernel Geometries for Structure-Preserving Representation Learning

**Himanshu Singh**  
Department of Meteorology and Atmospheric Science  
The Pennsylvania State University

**Accepted at NeurIPS 2026 — GlobalSouthAI**

---

## Overview

Can the geometry of a representation space be constructed so that a prescribed operator becomes exactly isometric?

This work approaches structure-preserving representation learning from an **inverse geometric perspective**. Rather than modifying an operator to respect a predetermined geometry, we construct a reproducing kernel Hilbert space (RKHS) geometry that respects the operator.

Consider a finite-dimensional function space

$$
\mathcal{V} = \operatorname{span}\{\psi_1,\ldots,\psi_m\},
$$

and a linear operator $T:\mathcal{V}\to\mathcal{V}$ represented by a matrix $M$.

For a Hermitian positive-definite matrix $G$, define the geometry

$$
\langle f_c,f_d\rangle_G = d^*Gc.
$$

The operator acts isometrically in this geometry precisely when

$$
\boxed{M^*GM=G.}
$$

Thus, the central question becomes:

> **For a prescribed operator $M$, when does there exist a positive-definite geometry $G$ in which $M$ becomes an exact isometry?**

---

## Main Results

### 1. Existence of an invariant RKHS geometry

There exists a Hermitian positive-definite matrix $G$ satisfying

$$
M^*GM=G
$$

if and only if $M$ is similar to a unitary matrix.

Equivalently,

$$
M \text{ is diagonalizable}
\qquad\text{and}\qquad
\sigma(M)\subset\mathbb{T},
$$

where

$$
\mathbb{T}=\{z\in\mathbb{C}:|z|=1\}.
$$

Therefore, unit-circle spectrum alone is not sufficient: nontrivial Jordan blocks provide an obstruction to an exact invariant positive-definite geometry.

---

### 2. Complete classification of invariant geometries

Suppose

$$
M=SDS^{-1},
$$

where the distinct eigenvalues of $M$ are $\mu_1,\ldots,\mu_r$ with multiplicities $m_1,\ldots,m_r$.

Then every invariant positive-definite geometry has the form

$$
G
=
S^{-*}
\operatorname{diag}(H_1,\ldots,H_r)
S^{-1},
$$

where

$$
H_j\in\mathbb{H}_{++}^{m_j}.
$$

Consequently,

$$
\mathcal{G}(M)
\cong
\prod_{j=1}^{r}\mathbb{H}_{++}^{m_j},
$$

and

$$
\dim_{\mathbb{R}}\mathcal{G}(M)
=
\sum_{j=1}^{r}m_j^2.
$$

Hence, the **spectral multiplicities determine the degrees of freedom in the invariant representation geometry**.

---

### 3. Operator-adapted reproducing kernels

For the finite-dimensional RKHS construction used in the paper, the reproducing kernel associated with $G$ is

$$
k_G(x,y)
=
\Psi(x)^*G^{-1}\Psi(y).
$$

The complete family of operator-adapted kernels is therefore determined by the complete family of positive-definite solutions of

$$
M^*GM=G.
$$

This reverses the usual perspective:

> Instead of fixing a kernel geometry and asking how an operator behaves within it, we fix the operator and construct the geometry in which it has the desired structure.

---

## Operator-Adapted Gaussian Kernel

The same geometric principle can be incorporated into standard kernel families.

Consider a transformation

$$
A=SQS^{-1},
$$

where $Q$ is unitary and $S$ is invertible. Define

$$
G=S^{-*}S^{-1}.
$$

Then

$$
A^*GA=G.
$$

The corresponding operator-adapted Gaussian kernel is

$$
k_G(x,y)
=
\exp\left(
-\frac{(x-y)^*G(x-y)}{2\gamma^2}
\right).
$$

Because $A^*GA=G$,

$$
k_G(Ax,Ay)=k_G(x,y).
$$

Thus, a transformation that is non-unitary in Euclidean geometry can preserve pairwise similarity exactly in an appropriately adapted RKHS geometry.

---

## Numerical Verification

The paper illustrates the construction using a $20$-dimensional linear representation operator that is similar to a unitary matrix but is not unitary in the native Euclidean geometry.

The experiment uses

$$
d=20,\qquad N=120,\qquad \gamma=3.
$$

We compare the standard Gaussian kernel

$$
k_0(x,y)
=
\exp\left(
-\frac{\|x-y\|_2^2}{2\gamma^2}
\right)
$$

with the operator-adapted Gaussian kernel

$$
k_G(x,y)
=
\exp\left(
-\frac{(x-y)^*G(x-y)}{2\gamma^2}
\right).
$$

For a kernel $k$, the pairwise invariance discrepancy is

$$
\Delta_k(i,j)
=
\left|
k(Mz_i,Mz_j)-k(z_i,z_j)
\right|.
$$

The normalized invariance error is

$$
\varepsilon_k
=
\frac{
\left(
\sum_{i,j=1}^{N}
\left|
k(Mz_i,Mz_j)-k(z_i,z_j)
\right|^2
\right)^{1/2}
}{
\left(
\sum_{i,j=1}^{N}
|k(z_i,z_j)|^2
\right)^{1/2}
}.
$$

The resulting errors are:

| Kernel | Normalized invariance error |
|:---|---:|
| Standard Gaussian | $5.61\times10^{-1}$ |
| Operator-adapted Gaussian | $1.12\times10^{-15}$ |

The adapted geometry therefore recovers kernel invariance to numerical precision while leaving the operator spectrum unchanged.

---

## Repository Structure

```text
operator-adapted-rkhs/
│
├── README.md
├── LICENSE
├── requirements.txt
├── CITATION.cff
│
├── paper/
│   └── operator_adapted_rkhs.pdf
│
├── src/
│   └── operator_adapted_rkhs.py
│
├── experiments/
│   └── reproduce_figure1.py
│
└── figures/
    └── figure1.png
```

---

## Paper

**Operator-Adapted Reproducing Kernel Geometries for Structure-Preserving Representation Learning**

Himanshu Singh  
The Pennsylvania State University

**NeurIPS 2026 — GlobalSouthAI**

The paper develops the existence and classification theory for operator-adapted RKHS geometries and demonstrates the construction through an operator-adapted Gaussian kernel.

---

## Citation

If you find this work useful, please cite:

```bibtex
@inproceedings{singh2026operatoradapted,
  title     = {Operator-Adapted Reproducing Kernel Geometries for
               Structure-Preserving Representation Learning},
  author    = {Singh, Himanshu},
  booktitle = {NeurIPS 2026 GlobalSouthAI},
  year      = {2026}
}
```

---

## License

This repository is released under the MIT License.
