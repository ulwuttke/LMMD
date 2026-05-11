# Equilibrium and basic equations of the linear theory


## Eqilibrium in 1 dim.

If a simple one dimansional truss is loded by a line load $f$, the stresses, or the normal force $N$ is not constant. 

![Equi1dim](Equi1dim.png)

The equation for static equilibrium is: 

$0=-N+f\cdot dx+N+dN = f\cdot dx+dN $

The equation can be rewritten:

$ 	\begin{matrix}
0 & = & f\cdot dx+dN & |\cdot \frac{1}{dx}\\
0 & = & f+ \frac{dN}{dx}
\end{matrix}$

So, the change in the normal force $\frac{dN}{dx}$ relating to an infinitesimally small length element $dx$ corresponds to the applied line load $f$

Please note that the internel load distribution can be calculated directly from the equilibrium equations.

## Eqilibrium in 2 or 3 dim.

there are two differences in three dimensions. First, it is more confusing, second, the shear stress has to be includet. Because it is easyer tu understand, the following picture is only sketched in two dimensions as a thin plate with the plane dimension $dx_1$, $dx_2$ and the thikness $dx_3$. The volume-load $f$ is a *force per volume*.

![Equi2dim](Equi2dim.png)

The equilibrium of forces and moments can be written like this (remember: the resulting force is e.g. $\text{stress}\cdot\text{area}=\sigma_{11}\cdot dx_2\, dx_3$):

$\begin{matrix}
\text{a.}&\rightarrow\,: & 0 = & (\sigma_{11} + \partial \sigma_{11}) \cdot dx_2\cdot dx_3 - \sigma_{11} \cdot dx_2\cdot dx_3\\
&&& + (\sigma_{21} + \partial \sigma_{21})\cdot dx_1\cdot dx_3 - \sigma_{21}\cdot dx_1\cdot dx_3\\
&&& + f_1 \cdot dx_1 \cdot dx_2\cdot dx_3 \\
&&&&\\
\text{b.}&\uparrow\,: & 0 = & (\sigma_{22} + \partial \sigma_{22})\cdot dx_1\cdot dx_3 - \sigma_{22} \cdot dx_1\cdot dx_3\\
&&& + (\sigma_{12} + \partial \sigma_{12})\cdot dx_2\cdot dx_3 - \sigma_{12}\cdot dx_2\cdot dx_3\\
&&& + f_1 \cdot dx_1 \cdot dx_2\cdot dx_3 \\
&&&&\\
\text{c.}&\curvearrowright\,:& 0 = &(\sigma_{21} + \partial \sigma_{21})\cdot dx_1\cdot dx_3\cdot\frac{dx_2}{2} +\sigma_{21} \cdot dx_1\cdot dx_3\cdot\frac{dx_2}{2}\\
&&&-(\sigma_{12} + \partial \sigma_{12})\cdot dx_2\cdot dx_3\cdot\frac{dx_1}{2} +\sigma_{12} \cdot dx_2\cdot dx_3\cdot\frac{dx_1}{2}\\
\end{matrix}$

Form equation $\text{c.}$ is resulting that $\partial \sigma_{12}=\partial \sigma_{21}$

Equations $\text{a.}$ and $\text{b.}$ simlifies to 

$\begin{matrix}
0&=&\partial \sigma_{11} \cdot dx_2+\partial \sigma_{21}\cdot dx_1  + f_1 \cdot dx_1 \cdot dx_2\\
0&=&\partial \sigma_{12} \cdot dx_2+\partial \sigma_{22}\cdot dx_1  + f_1 \cdot dx_1 \cdot dx_2
\end{matrix}$

or

$\begin{matrix}
0&=&\frac{\partial \sigma_{11}}{\partial x_1}+\frac{\partial \sigma_{21}}{\partial x_2}  + f_1 \\
0&=&\frac{\partial \sigma_{12}}{\partial x_1}+\frac{\partial \sigma_{22}}{\partial x_2}  + f_2 \\
\end{matrix}$

or, at last

$\begin{matrix}
0&=&\frac{\partial \sigma_{ik}}{\partial x_i}+ f_k \\
\end{matrix}$


**Note:** Even it looks like one equation, it is a set of (in three dim.) three equations for six unkown stresses. So this set of equations is not sufficient to solve problems in kontinuum mechanics. 

## basic equations of the linear theory

|    | equation    |  number of equations | known quantities | unknown quantities |
| :------ | :-----: | :-------: |:-------: | :-------: |
| equilibrium | $0=\frac{\partial \sigma_{ik}}{\partial x_i}+ f_k$ | 3 | 3 ($f_k$) | $6$ ($\sigma_{ik}$) |
| kinematik | $\epsilon_{lm}=\frac{1}{2}(\frac{\partial u_l}{\partial x_m}+\frac{1}{2}(\frac{\partial u_m}{\partial x_l})$ | 6 | 0 | $6+3=9$ ($\epsilon_{ik}$, $u_l$)|
| sum |  |  9  | | 15 |

The 9 equations derived so far contain 15 unknowns. Therefore, additional equations - exact $15-9=6$ equations - are still needed, which are found by including the material (for theoretical background see [constitutive equations](https://en.wikipedia.org/wiki/Constitutive_equation)). 

For the linear theorie a linear relation (linear map) between the stresses and strains is assumend:

$\sigma_{ik}=E_{iklm}\cdot\epsilon_{lm}$

If the material parameters are known (here all the $3\cdot 3\cdot 3\cdot3=81$ components for the elasic 4th-order tensor $E_{iklm}$), the material equations has no additional unknown quantities but gives 6 - exact the 6 equations needet - additional equations. 



