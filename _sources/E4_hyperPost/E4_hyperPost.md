# HyperView Postprocessing 

## Vector components

The deformation is an example for a vector component (1st-order tensor) and can be shown in different ways:

```{dropdown} Contur plot: In this case the x-coponent of the deformaion is shown; here x refers to the global system
![HyperViewContPlDef](HyperViewContPlDef.JPG)
```

```{dropdown} Vector plot: The resulting deformation is shown as a vector in every element; here the total/resulting deformation is shown, this is the same in any coordinate system
![HyperViewVecPlDef](HyperViewVecPlDef.JPG)
```

## Tensor components

Stress and strain are examples of tensor (2nd-order tensor) components. In addition to the contour plot, the principal stresses or the tensor components can be displayed. The principal stresses are shown in the principal directions; the components refer to the selected coordinate system
```{dropdown} Tensor plot: stress-tensor, golobal system
![HyperViewTenPlStGl](HyperViewTenPlStGl.jpg)
```

```{dropdown} Tensor plot: stress-tensor, USER system
![HyperViewTenPlStUser](HyperViewTenPlStUser.jpg)
```

To get the results, the *table*-button can be used to create a "query table". 

```{dropdown} Query table
![HyperViewTabelResStrain](HyperViewTabelResStrain.jpg)
```



**Exercise:**

1. carry out a fem-analysis with a defined USER coordinate system
2. show the components of the stress tensor in the global system; read out all stress compnents in the global system at one position of the model and combine the stress values in the stress tensor (global system)
3. show the components of the stress tensor in the global system; read out all stress compnents in the USER system at the same position of the model and combine the stress values in the stress tensor (USER-system)
4. create the transformation tensor $\boldsymbol{\alpha}$ for the transformation from the global in the user system
5. transform the stress tensor from the local into the global system and compare the results
