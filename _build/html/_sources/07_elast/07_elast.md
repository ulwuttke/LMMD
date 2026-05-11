# linear theory of elasticity

The linear elastic tensor $\boldsymbol{E}=E_{iklm}$ has in three dimensions $3\cdot 3\cdot 3\cdot3=81$ components or elastic material Parameters. Fortunately the number of elastic parameters can be reduced:

## symmetrie in $\boldsymbol{E}$

Because $\boldsymbol{\sigma}=\sigma_{ik}=\boldsymbol{\sigma}^T=\sigma_{ki}$ and $\boldsymbol{\epsilon}=\epsilon_{lm}=\boldsymbol{\epsilon}^T=\epsilon_{ml}$ are symmetric tensors, there is a symmetrie in $\boldsymbol{E}$ as well:

$E_{iklm}=E_{kilm}=E_{kiml}=E_{ikml}$

This leads for example to

$\begin{matrix}
\sigma_{11}=&E_{11\,11}\cdot\epsilon_{11}+E_{11\,12}\cdot\epsilon_{12}+E_{11\,13}\cdot\epsilon_{13}+\\
&E_{11\,21}\cdot\epsilon_{21}+E_{11\,22}\cdot\epsilon_{22}+E_{11\,23}\cdot\epsilon_{23}+\\
&E_{11\,31}\cdot\epsilon_{31}+E_{11\,32}\cdot\epsilon_{32}+E_{11\,33}\cdot\epsilon_{33}+
\end{matrix}$

with 6 different coefficients: 

$E_{11\,11}$, $E_{11\,22}$, $E_{11\,33}$, $E_{11\,12}=E_{11\,21}$, $E_{11\,13}=E_{11\,31}$, $E_{11\,23}=E_{11\,32}$

For every of the 6 different stesses in the stress tensor it is the same, so there are only $6\cdot 6=36$ coefficients instead of $81$, which can be written in a 6x6 matrix:

$\begin{bmatrix}
\sigma_{11}\\ \sigma_{22}\\ \sigma_{33}\\  \sigma_{23}\\ \sigma_{13}\\ \sigma_{12}
\end{bmatrix} = 
\begin{bmatrix}
a_{11}&a_{12}&a_{13}&a_{14}&a_{15}&a_{16}\\
a_{21}&a_{22}&a_{23}&a_{24}&a_{25}&a_{26}\\
a_{31}&a_{32}&a_{33}&a_{34}&a_{35}&a_{36}\\
a_{41}&a_{42}&a_{43}&a_{44}&a_{45}&a_{46}\\
a_{51}&a_{52}&a_{53}&a_{54}&a_{55}&a_{56}\\
a_{61}&a_{62}&a_{63}&a_{64}&a_{65}&a_{66}\\
\end{bmatrix} \cdot
\begin{bmatrix}
\epsilon_{11}\\ \epsilon_{22}\\ \epsilon_{33}\\  \epsilon_{23}=\frac{1}{2}\gamma_{23}\\ \epsilon_{13}=\frac{1}{2}\gamma_{13}\\ \epsilon_{12}=\frac{1}{2}\gamma_{12}
\end{bmatrix}$

The elastic components are assigned as follows:

$E_{11\,11}=a_{1\,1}$; $E_{11\,12}=a_{1\,6}$; $E_{11\,13}=a_{1\,5}$; and so on 

So two old indices are combined to one new index:

$11\rightarrow 1$; $22\rightarrow 2$; $33\rightarrow 3$; $23\text{ or }32\rightarrow 4$; $13\text{ or }31\rightarrow 5$; $12\text{ or }21\rightarrow 6$

## existence of an elastic potential


## Assumptions regarding the symmetry of the material


### monoclinic


### orthotropic


### traverse isotropic


### isotropic


