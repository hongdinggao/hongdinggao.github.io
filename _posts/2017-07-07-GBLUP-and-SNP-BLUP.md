---
layout: post
title:  GBLUP and SNP BLUP
comments: true
categories: genomics
author: Hongding Gao
---

Here are just some simple notes about these 2 equivalent models

#### MME for GBLUP
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


where $\sigma^2_a$ is the total genetic variance, $$\lambda=\sigma^2_e/\sigma^2_a$$      
$$\mathbf{u}\;\sim\;N(\mathbf{0},\mathbf{G}\sigma^2_a)$$


#### Model for SNP-BLUP
The marker effects $\mathbf{g}_i$ were
assumed to be identically and independently distributed


$$
\mathbf{y=1\mu + Mg + e}
$$

where  
$$\mathbf{g}\;\sim\;N(\mathbf{0},\mathbf{I}\sigma^2_g)$$    
$$\mathbf{e}\;\sim\;N(\mathbf{0},\mathbf{D}\sigma^2_e)$$


where  
$$d_{ii} = 1/\omega_i$$   
$$\omega_i = EDC_i/\lambda$$



**MME**  


$$
   \left[
     \begin{array}{cc}
       \mathbf{X'R}^{-1}\mathbf{X} &  \mathbf{X'R}^{-1}\mathbf{Z}\\
       \mathbf{Z'R}^{-1}\mathbf{X} &  \mathbf{Z'R}^{-1}\mathbf{Z}+(\mathbf{I}\sigma^2_g)^{-1}
     \end{array}\right]
    \left[
     \begin{array}{c}
        \hat{\mathbf{b}}\\
        \hat{\mathbf{a}}
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
       \mathbf{Z'}\mathbf{X} &  \mathbf{Z'}\mathbf{Z}+\mathbf{I}\lambda
     \end{array}\right]
    \left[
     \begin{array}{c}
        \hat{\mathbf{b}}\\
        \hat{\mathbf{a}}
     \end{array}\right]
=
    \left[
     \begin{array}{c}
        \mathbf{X'}\mathbf{y}\\
        \mathbf{Z'}\mathbf{y}
     \end{array}\right]
$$

where   
$$\sigma^2_g$$ is the SNP variance for each SNP  
$$\lambda=\sigma^2_e/\sigma^2_g$$   
$$\sigma^2_a=2\sum_{i=1}^mp_iq_i\sigma^2_g$$




The DGV  

$$
\mathbf{\hat{a} = 1\hat{\mu} + M\hat{g}}
$$


