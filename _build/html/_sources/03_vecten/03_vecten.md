# vector/tensor rotation and transformation

## definitions


| physical quantity | descr. | example | tensor order |
| ---- | ---- | ---- |:----:|
| scalar: | one informatoin (magnitude) | temperature, energy | 0 |
| vector: | two informatoin (magnitude and direction) | velocity, force | 1 |
| tensor: | more than two informatoin |  |  |
| |  | stress tensor | 2 |
|  |  | elastic tensor | 4 |


## scalar- /inner- / dot- product

[see](https://en.wikipedia.org/wiki/Dot_product)

vector definition (here only in 2 dim.):  
$\vec{c} = \boldsymbol{c} = c_1 \boldsymbol{e}^1 + c_2 \boldsymbol{e}^2 = \sum_{i=1}^{i=2} c_i \boldsymbol{e}^i = c_i \boldsymbol{e}^i $  
The simplification $\sum_{i=1}^{i=2} c_i \boldsymbol{e}^i = c_i \boldsymbol{e}^i $ is called EINSTEIN-notation.

---
**NOTE**

It is not importent, wich letter is used for the index, but it is very important wich index has the same letter ([EINSTEIN Summation](https://en.wikipedia.org/wiki/Einstein_notation) )! So, equal indices were used as summation indeces - and they dissapear after the summation.  
for. ex.: $c_i \cdot d^k = M_i^{ k}$ (result is a tensor 2nd grade); $c_n \cdot d^n = n$ (result a scalar) 


---


$c_i \boldsymbol{e}^i $ are the covariant components of the vector $\vec{c} = \boldsymbol{c}$

$c^i \boldsymbol{e}_i $ are the contravariant components of the vector $\vec{c} = \boldsymbol{c}$

the two basis systems $\boldsymbol{e}^i$ and the  so called dual basis $\boldsymbol{e}_i$ are linked by the following condition:

$\boldsymbol{e}^1 \cdot $\boldsymbol{e}_1 =1$, $\boldsymbol{e}^2 \cdot $\boldsymbol{e}_2 =1$, $\boldsymbol{e}^1 \cdot $\boldsymbol{e}_2 =0$, $\boldsymbol{e}^2 \cdot $\boldsymbol{e}_1 =0$

![DualBasis](DualBAsis.png)

Using the dual basis the scala product of two vectors (in two dim.) can be written:

$\boldsymbol{c}\cdot\boldsymbol{d}= [c_1 \boldsymbol{e}^1 + c_2 \boldsymbol{e}^2] \cdot [b_1 \boldsymbol{e}^1 + b_2 \boldsymbol{e}^2] = c_1 b^1 \boldsymbol{e}^1 \boldsymbol{e}_1 + c_1 b^2 \boldsymbol{e}^1 \boldsymbol{e}_2 + c_2 b^1 \boldsymbol{e}^2 \boldsymbol{e}_1 + c_2 b^2 \boldsymbol{e}^2 \boldsymbol{e}_2$ = c_1 b^1+c_2 b^2$

One can see, that using the dual basis by using one vector with the co- and the other vector with the contravariant components, the basis vectors are "disappearing" and a scalar ramains. This is important, if the basis vectors are not orthonormal.

![WikiCoContra](https://upload.wikimedia.org/wikipedia/commons/7/72/Covariantcomponents.gif)

[co- contravariant basis](https://en.wikipedia.org/wiki/Covariance_and_contravariance_of_vectors)

Using the EINSTEIN-notation the scalar product can be writen like

$\boldsymbol{c}\cdot\boldsymbol{d}= c_{i} \boldsymbol{e}^i \cdot b_j \boldsymbol{e}^j = c_i b^j \boldsymbol{e}^i \boldsymbol{e}_j$

The product $ \boldsymbol{e}^i \boldsymbol{e}_j$ results in the Identity matrix $\delta_i^j$:

$\boldsymbol{e}^i \boldsymbol{e}_j=
\begin{bmatrix}
1 & 0\\
0 & 1
\end{bmatrix} = \delta_i^j$

$c_i b^j \boldsymbol{e}^i \boldsymbol{e}_j=c^i_j = c_i b^i =c_j b^j$


*EXAMPLES*

$c_i\cdot b^i = $  
$c_j\cdot b^i = $  
$A_{ji}\cdot B_{ck} = $  
$A_{ji}\cdot B_{ik} = $  
$A_{ji}\cdot B_{ij} = $  


## tensor/vector transformation

The vector $\boldsymbol{b}$ is given in the "old" basis system $\boldsymbol{e}^i$ (old basis indes lower case). The components should betransformed in the new basis system $\hat{\boldsymbol{e}}^J$ (new basis indes upper case).
![vectordiffbase](VecDiffBase.png)

$\boldsymbol{b}=b_i\cdot \boldsymbol{e}^i = \hat{b}_i\cdot \hat{\boldsymbol{e}}^J$  

$b_i\cdot \boldsymbol{e}^i = \hat{b}_i\cdot \hat{\boldsymbol{e}}^J \,| \cdot \hat{\boldsymbol{e}}_K$  
$b_i\cdot \hat{\boldsymbol{e}}_K \cdot \boldsymbol{e}^i = \hat{b}_i\cdot \hat{\boldsymbol{e}}^J  \cdot \hat{\boldsymbol{e}}_K$ 

$\hat{\boldsymbol{e}}^J  \cdot \hat{\boldsymbol{e}}_K = \delta_K^J$
$\hat{\boldsymbol{e}}_K \cdot \boldsymbol{e}^i = \alpha_K^i$

so

$\alpha_K^i \cdot b_i=\hat{b}_K$

with

$\alpha_K^i=
\begin{bmatrix}
\hat{\boldsymbol{e}}_1 \cdot \boldsymbol{e}^1 & \hat{\boldsymbol{e}}_1 \cdot \boldsymbol{e}^2 & ...\\
\hat{\boldsymbol{e}}_2 \cdot \boldsymbol{e}^1 & \hat{\boldsymbol{e}}_2 \cdot \boldsymbol{e}^2 & ...\\
... & &\\
\end{bmatrix}$

If the new basis can be described with the old basis, the components of $\boldsymbol{\alpha}$ can be calculated:

$\hat{\boldsymbol{e}}_1=\hat{e}_1^{\,1}\cdot \boldsymbol{e}_1 + \hat{e}_2^{\,1}\cdot \boldsymbol{e}_2 + ...$  

or in index-notation  

$\hat{\boldsymbol{e}}_K=\hat{e}_K^{\,j}\cdot \boldsymbol{e}_j$  
$ \Rightarrow \hat{\boldsymbol{e}}_K \cdot \boldsymbol{e}^i = \hat{e}_K^{\,j}\cdot \boldsymbol{e}_j \cdot \boldsymbol{e}^i = \hat{e}_K^{\,j} \cdot \delta_j^{\,i}= \hat{e}_K^{\,j} = \alpha_K^{\,j}$  

$\alpha_K^i=
\begin{bmatrix}
\hat{\hat{e}}_1^{\,1} & \hat{\hat{e}}_1^{\,2}  & ...\\
\hat{\hat{e}}_2^{\,1}  & \hat{\hat{e}}_2^{\,2}  & ...\\
... & &\\
\end{bmatrix}$

Each row is a list of the components of each vector of the new basis referred to the old basis. This works evan for non orthonormal basis systems.


---
** NOTE **
In the following we will use only orthonormal coordinate systems. Here is: $\boldsymbol{e}_i=\boldsymbol{e}^i$. For that reason there is no need to distinguish between co- and contravariant basis. So all indices will be written as al lower index.
---

*EXAMPLE"
Define $\boldsymbol{\alpha}} for a rotaion of a orthonormal basis 
