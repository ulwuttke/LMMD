# Failure analysis

## Classic material failure criteria for isotropic materials

### Maximum principal stress criterion for brittle materials

The idea of the [maximum principal stress criterion](https://en.wikipedia.org/wiki/Material_failure_theory#Phenomenological_failure_criteria) is, that a material fails when the maximum principal stress $\sigma^1$ exceeds the uniaxial tensile strength of the material:

$\sigma^1<\sigma_T=R_m$

This criterion is used in the fracture analysis of brittle materials. 


### von Mises yield criterion for ductile materials

The von [Mises yield-criterion](https://en.wikipedia.org/wiki/Von_Mises_yield_criterion) states that yielding begins as soon as the energy of distortion caused by the load reaches a threshold value in the material. The criterion in form of an equivalent stress $\sigma_{v Mises}$ is the most commonly used yield criterion in engineering:

$\sigma_{v Mises}=f(\sigma_{ik})<\sigma_F=R_e$

The elastic deformation energy, or, more precisely, the elastic strain energy denity $w$ is described in a one dimensional case and a linear stress-strain ralation by:

$w= \int_{}^{} \sigma \, \mathrm{d}\epsilon=\frac{1}{2} \sigma \cdot \epsilon$

or in tree dimensions by:

$w= \int_{}^{} \sigma_{ik} \, \mathrm{d}\epsilon_{ik}=\frac{1}{2} \sigma_{ik} \cdot \epsilon_{ik}$

The strain energy density $w$ consists of two components - volumetric and distortional. To seperate the distortional energy from the total energy the stress and strain tensor are devided in a hydrostatic (volume change) and a deviatoric (distortion) part:


$\sigma_{ik}=\frac{1}{3}\,\sigma_{ll}\,\delta_{ik}+s_{ik}$  
$\epsilon_{ik}=\frac{1}{3}\,\epsilon_{nn}\,\delta_{ik}+e_{ik}$ 

The first term is the hydrostatc stress resp. strain, the second term is the deviatoric stress tensor $s_{ik}$ resp. $e_{ik}$.

Now $w$ can be written as:

$
\begin{matrix}
w & = & \frac{1}{2} \sigma_{ik} \cdot \epsilon_{ik}\,\,\,\,\,\\
 & = & \frac{1}{2} (\frac{1}{3}\,\sigma_{ll}\,\delta_{ik}+s_{ik})(\frac{1}{3}\,\epsilon_{nn}\,\delta_{ik}+e_{ik})\\
  & = & \frac{1}{2} ( \frac{1}{3}\,\sigma_{ll}\,\delta_{ik}\cdot\frac{1}{3}\,\epsilon_{nn}\,\delta_{ik} + \frac{1}{3}\,\sigma_{ll}\,\delta_{ik}\cdot e_{ik} +\\
&&                    s_{ik}\cdot\frac{1}{3}\,\epsilon_{nn}\,\delta_{ik} + s_{ik}\cdot e_{ik})\\
\end{matrix}
$

The second and third term are equal to zero, because the product $s_{ik}\cdot\delta_{ik}$ resp. $e_{ik}\cdot\delta_{ik}$ is equal to zero because for exampe:

$
\begin{matrix}
s_{ik}\cdot\delta_{ik}&=&s_{11}+s_{22}+s_{33}\\
&=&(\sigma_{11}-\frac{1}{3}(\sigma_{11}+\sigma_{22}+\sigma_{33}))\,+\\
&&(\sigma_{22}-\frac{1}{3}(\sigma_{11}+\sigma_{22}+\sigma_{33}))\,+\\
&&(\sigma_{33}-\frac{1}{3}(\sigma_{11}+\sigma_{22}+\sigma_{33}))\,\,\,\\
&=&\sigma_{11}+\sigma_{22}+\sigma_{33}-3\cdot\frac{1}{3}(\sigma_{11}+\sigma_{22}+\sigma_{33})=0\\
\end{matrix}
$

So $w$ can be written as:

$w=\frac{1}{6}\sigma_{ll}\,\epsilon_{nn}+\frac{1}{2}s_{ik}\,e_{ik}$

with the energy of distortion 

$w_d=\frac{1}{2}s_{ik}\,e_{ik}$

The linear elastic material law can be written in a tensor equation:

$\epsilon_{ik}=\frac{1+\nu}{E}(\sigma_{ik}-\frac{\nu}{1+\nu}\delta_{ik}\,\sigma_{ll})$

If the stress tensor has only a deviatoric component, even the strain tensor has only a deviatoric component and the equation simplifies because of $s_{ll}=0$ to

$e_{ik}=\frac{1+\nu}{E}s_{ik}$

and so the energy of distortion is

$w_d=\frac{1}{2}s_{ik}\,e_{ik}=\frac{1+\nu}{2\cdot E}s_{ik}\,s_{ik}$

and so only depending on the deviatoric part of the stress tensor. 

To get the von Mises equivalent stress $\sigma_{v Mises}=\sigma_{v}$, the energy of distortion of a uniaxial stress $w_d^{uni}$ is set equal to the energy of distortion of a three dimensional stress state $w_d$. 


$
\sigma^{uni}_{lm}=
\begin{bmatrix}
\sigma_{v}&0&0\\
0&0&0\\
0&0&0\\
\end{bmatrix}=\frac{1}{3}\sigma_{v}
\begin{bmatrix}
1&0&0\\
0&1&0\\
0&0&1\\
\end{bmatrix}+
\begin{bmatrix}
\sigma_{v}-\frac{1}{3}\sigma_{v}&0&0\\
0&-\frac{1}{3}\sigma_{v}&0\\
0&0&-\frac{1}{3}\sigma_{v}\\
\end{bmatrix}
$

and 

$
\begin{matrix}
w^{uni}_d&=&\frac{1+\nu}{2\, E}s_{ik}\,s_{ik}\\
&=&\frac{1+\nu}{2\, E}((\sigma_{v}-\frac{1}{3}\sigma_{v})^2+(-\frac{1}{3}\sigma_{v})^2+(-\frac{1}{3}\sigma_{v})^2))\\
&=&\frac{1+\nu}{2\, E}((\frac{2}{3})^2+(-\frac{1}{3})^2+(-\frac{1}{3})^2)\sigma_v^2\\
&=&\frac{1+\nu}{2\, E}\cdot\frac{2}{3}\cdot\sigma_v^2\\
\end{matrix}$

beause $w_d^{uni}$ is set (or assumed) equal to $w_d$ it is:

$
\begin{matrix}
w^{uni}_d&=&w_d\\
\frac{1+\nu}{2\, E}\cdot\frac{2}{3}\cdot\sigma_v^2&=&\frac{1+\nu}{2\cdot E}s_{ik}\,s_{ik}\\
\end{matrix}$

$\Rightarrow \sigma_v=\sqrt{\frac{3}{2}\,s_{ik}\,s_{ik}}$


This expression is equal to

$\sigma_v=\frac{1}{\sqrt{2}}\sqrt{(\sigma^1-\sigma^2)^2+(\sigma^2-\sigma^3)^2+(\sigma^3-\sigma^1)^2}$

with the principal stresses $\sigma^1$, $\sigma^2$ and $\sigma^3$ or in case of only one normal stress $\sigma$ and one shear stress $\tau$

$\sigma_v=\sqrt{\sigma^2+3\,\tau^2}$



## Anisotropic failiure criterion acc. to VDI 2014 part 3

### in fibre fracture

### inter fibre fracture



