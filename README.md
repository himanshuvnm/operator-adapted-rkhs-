# Operator-Adapted Reproducing Kernel Geometries

<p align="center">
  <b>Construct the geometry to respect the operator — not the operator to respect a predetermined geometry.</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/NeurIPS%202026-GlobalSouthAI-blue" alt="NeurIPS 2026 GlobalSouthAI">
  <img src="https://img.shields.io/badge/RKHS-Operator%20Adapted-6A0DAD" alt="Operator-Adapted RKHS">
  <img src="https://img.shields.io/badge/Python-3.12%2B-blue" alt="Python 3.12+">
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="MIT License">
</p>

---

## Operator-Adapted Reproducing Kernel Geometries for Structure-Preserving Representation Learning

**Himanshu Singh**  
Department of Meteorology and Atmospheric Science  
College of Earth and Mineral Sciences  
The Pennsylvania State University  
University Park, PA 16802

**Accepted at GlobalSouthAI @ The Fortieth Annual Conference on Neural Information Processing Systems (NeurIPS 2026)**

**MSC:** 46-XX · 47B34 · 37-XX · 68Txx

---

## 🔎 The Question

Representation learning typically starts with a prescribed or learned geometry and subsequently asks how an operator behaves within that space.

This work reverses that order.

> **Given an operator, can we construct a reproducing kernel Hilbert space (RKHS) geometry in which the operator becomes exactly structure-preserving?**

Instead of adapting the **operator to the geometry**, we investigate how to adapt the **geometry to the operator**.

---

## 💡 Main Idea

We develop a finite-dimensional theory of **operator-adapted reproducing kernel geometries**.

The central message is simple:

> **An operator that is not unitary in its original representation geometry may become exactly unitary after an appropriate change of RKHS geometry.**

This leads to an inverse geometric viewpoint on representation learning in which the desired operator structure is prescribed first and the compatible representation geometry is constructed around it.

---

## 🧭 What the Theory Establishes

The paper addresses three interconnected questions.

### 1. Existence

We characterize precisely when a prescribed finite-dimensional linear operator admits a positive-definite RKHS geometry in which its action is isometric.

### 2. Classification

When such a geometry exists, we characterize the **complete family** of admissible invariant RKHS geometries and their corresponding reproducing kernels.

### 3. Geometric Degrees of Freedom

The spectral structure does more than determine whether an invariant geometry exists. The **eigenvalue multiplicities determine the degrees of freedom** available in the family of operator-adapted geometries.

This provides a direct bridge between

**operator spectrum → invariant geometry → reproducing kernel representation.**

---

## 🔬 Numerical Illustration

<p align="center">
  <img src="example_1.png" width="100%" alt="Numerical illustration of operator-adapted RKHS geometry">
</p>

<p align="center">
  <i>
  A spectrally stable operator can remain geometrically non-isometric.
  Adapting the representation geometry restores exact invariance without changing the spectrum.
  </i>
</p>

The figure illustrates the construction in a **20-dimensional representation space**.

### (a) Same spectrum, different geometry

The original operator has its eigenvalues on the unit circle. The adaptation leaves these eigenvalues unchanged.

The construction therefore does **not** alter the underlying spectral dynamics.

### (b) Spectral stability is not geometric invariance

Despite having unimodular eigenvalues, the singular values of the original operator differ substantially from one. It is therefore non-isometric in the native Euclidean geometry.

After adapting the geometry, the singular values collapse to one: the same operator becomes unitary in the adapted representation.

### (c) Standard Gaussian RBF: similarity is distorted

Under the standard Gaussian kernel, applying the operator substantially changes pairwise kernel similarities.

**Normalized invariance error: 5.61 × 10⁻¹**

### (d) Operator-adapted Gaussian RBF: similarity is preserved

Once the invariant geometry is incorporated into the Gaussian kernel, the pairwise discrepancies collapse to numerical precision.

**Normalized invariance error: 1.12 × 10⁻¹⁵**

---

## ✨ Interpretation

The experiment highlights an important distinction:

> **Spectral preservation does not necessarily imply geometric preservation.**

An operator may possess the desired spectral structure while strongly distorting distances and similarities in the representation space.

The operator-adapted construction addresses this mismatch at the level of the **geometry itself**.

The result is a representation in which the same underlying operator becomes structure-preserving without changing its spectrum.

---

## 🧠 Conceptual Takeaway

The conventional viewpoint is

> **Choose the geometry → study or modify the operator.**

The viewpoint developed here is

> **Choose the operator → characterize and construct compatible geometries.**

This inversion is the central organizing principle of the work.

---

## 📄 Paper

### Operator-Adapted Reproducing Kernel Geometries for Structure-Preserving Representation Learning

**Himanshu Singh**  
The Pennsylvania State University

**GlobalSouthAI @ NeurIPS 2026**

The paper develops the existence and classification theory for operator-adapted RKHS geometries and demonstrates how the same principle produces an operator-adapted Gaussian kernel.

---

## 💬 Peer-Review Highlights

The work was accepted following peer review at **GlobalSouthAI @ NeurIPS 2026**.

> **“Excellent idea, theoretical arguments, and derivations.”**  
> — Program Chairs

> **“The paper's idea is simple yet novel, breaking away from conventional thinking.”**  
> — Reviewer HFTU

> **“The main characterization and classification are clear and useful.”**  
> — Reviewer ApH1

The reviews particularly highlighted the **inverse operator–geometry perspective**, the theoretical characterization of invariant geometries, and the concrete operator-adapted Gaussian construction.

For transparency, the complete reviews — including reviewer criticisms and limitations — are available through the paper's OpenReview page.

---

## 🌱 Scope and Next Direction

The present theory concerns **finite-dimensional function spaces**.

A natural next question is whether an analogous intrinsic classification can be developed for infinite-dimensional RKHSs, where the invariant geometry itself becomes an operator and additional questions of boundedness, invertibility, and kernel realization arise.

This provides a path from the finite-dimensional classification developed here toward a broader theory of **operator-adapted Hilbert geometries**.

---

## 📚 Citation

If this work is useful in your research, please cite:

```bibtex
@inproceedings{singh2026operatoradapted,
  title     = {Operator-Adapted Reproducing Kernel Geometries for
               Structure-Preserving Representation Learning},
  author    = {Singh, Himanshu},
  booktitle = {GlobalSouthAI Workshop at NeurIPS 2026},
  year      = {2026}
}
```

---

## 📜 License

Code in this repository is released under the **MIT License**.

© 2026 Himanshu Singh.
