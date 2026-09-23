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

Representation learning typically begins by choosing or learning a geometry and then studying how transformations behave within that representation space. This work considers the inverse problem: **given an operator, can we construct an RKHS geometry in which that operator exactly preserves the representation structure?**

We develop a finite-dimensional theory of **operator-adapted reproducing kernel geometries**. The results characterize precisely when such an invariant geometry exists and describe the complete family of reproducing kernels that realize it. A key consequence is that an operator need not be unitary in its original geometry to become unitary after an appropriate change of RKHS geometry.

The theory also reveals that the freedom available in constructing these geometries is governed by the spectral structure of the operator, with eigenvalue multiplicities determining the degrees of freedom in the family of admissible kernels.

We further show how this principle can be incorporated into standard kernel families through an operator-adapted Gaussian kernel. A numerical example demonstrates that a transformation that substantially distorts similarity under the standard Gaussian kernel can preserve it to numerical precision after adapting the geometry.

### Core idea

> **Rather than modifying an operator to respect a predetermined representation geometry, construct the geometry to respect the operator.**


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
