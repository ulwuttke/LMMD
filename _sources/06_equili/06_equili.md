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
&&&(\sigma_{12} + \partial \sigma_{12})\cdot dx_2\cdot dx_3\cdot\frac{dx_1}{2} +\sigma_{12} \cdot dx_2\cdot dx_3\cdot\frac{dx_1}{2}\\
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
