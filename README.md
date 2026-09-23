# Operator-Adapted Reproducing Kernel Geometries

[![NeurIPS 2026](https://img.shields.io/badge/NeurIPS%202026-GlobalSouthAI-blue)]()
[![Python](https://img.shields.io/badge/Python-3.12+-blue)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)]()

Official implementation accompanying:

**Operator-Adapted Reproducing Kernel Geometries for
Structure-Preserving Representation Learning**

**Himanshu Singh**  
Department of Meteorology and Atmospheric Science  
The Pennsylvania State University

**Accepted at NeurIPS 2026 — GlobalSouthAI**

---

## Overview

Can the geometry of a representation space be constructed so that a
prescribed operator becomes exactly isometric?

This work approaches structure-preserving representation learning from
an inverse perspective. Rather than modifying an operator to respect a
predetermined geometry, we construct an RKHS geometry that respects the
operator.

For a finite-dimensional representation

\begin{align*}
\mathcal V = \operatorname{span}\{\psi_1,\ldots,\psi_m\},
\end{align*}

with operator matrix \(M\), an RKHS geometry induced by
\(G \succ 0\) makes the operator isometric precisely when

\[
M^*GM = G.
\]

We show that such a positive-definite geometry exists if and only if
\(M\) is similar to a unitary matrix, equivalently when \(M\) is
diagonalizable with spectrum on the unit circle.

## Main Results

The repository illustrates three central results from the paper:

1. **Existence:** an exact invariant positive-definite geometry exists
   iff \(M\) is similar to a unitary matrix.

2. **Classification:** if

   \[
   M=SDS^{-1},
   \]

   the complete family of invariant metrics is

   \[
   G=S^{-*}\operatorname{diag}(H_1,\ldots,H_r)S^{-1},
   \]

   where the blocks correspond to distinct eigenspaces.

3. **Operator-adapted kernels:** the invariant metric can be incorporated
   into standard kernel families. For example,

   \[
   k_G(x,y)=
   \exp\left(
   -\frac{(x-y)^*G(x-y)}{2\gamma^2}
   \right).
   \]

## Numerical Verification

The paper considers a 20-dimensional operator that is similar to a
unitary matrix but is non-unitary in Euclidean geometry.

The experiment compares the standard Gaussian kernel with its
operator-adapted counterpart.

| Kernel | Normalized invariance error |
|---|---:|
| Standard Gaussian | \(5.61\times10^{-1}\) |
| Operator-adapted Gaussian | \(1.12\times10^{-15}\) |

The adapted geometry therefore recovers kernel invariance to numerical
precision without altering the operator spectrum.

## Reproducing Figure 1

```bash
git clone <repository-url>
cd operator-adapted-rkhs

python -m venv .venv
source .venv/bin/activate

pip install -r requirements.txt
python experiments/reproduce_figure1.py
