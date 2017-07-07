---
layout: post
title:  GBLUP and SNP BLUP
comments: true
categories: genomic
author: Hongding Gao
---

## Here are some simple notes about these 2 equivalent models

### MME for GBLUP
You can understand **GBLUP** is a "improved" version of
traditional **PBLUP**   




$$
   \left[
     \begin{array}{cc}
       \mathbf{X'R}^{-1}\mathbf{X} &  \mathbf{X'R}^{-1}\mathbf{Z}\\
       \mathbf{Z'R}^{-1}\mathbf{X} &  \mathbf{Z'R}^{-1}\mathbf{Z}+(\mathbf{G}\sigma^2_a)^{-1}
     \end{array}\right]
    \left[
     \begin{array}{c}
        \hat{\mathbf{b}}\\
        \hat{\mathbf{u}}
     \end{array}\right]
=
    \left[
     \begin{array}{c}
        \mathbf{X'R}^{-1}\mathbf{y}\\
        \mathbf{Z'R}^{-1}\mathbf{y}
     \end{array}\right]
$$


$$
   \left[
     \begin{array}{cc}
       \mathbf{X'}\mathbf{X} &  \mathbf{X'}\mathbf{Z}\\
       \mathbf{Z'}\mathbf{X} &  \mathbf{Z'}\mathbf{Z}+\mathbf{G}^{-1}\lambda
     \end{array}\right]
    \left[
     \begin{array}{c}
        \hat{\mathbf{b}}\\
        \hat{\mathbf{u}}
     \end{array}\right]
=
    \left[
     \begin{array}{c}
        \mathbf{X'}\mathbf{y}\\
        \mathbf{Z'}\mathbf{y}
     \end{array}\right]
$$


where $\sigma^2_a$ is the total genetic variance \quad
$\lambda=\sigma^2_e/\sigma^2_a$ \quad $\mathbf{u}\;\sim\;N(\mathbf{0},\mathbf{G}\sigma^2_a)$


