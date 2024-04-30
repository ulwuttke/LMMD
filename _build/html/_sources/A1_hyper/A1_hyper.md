# Using hyperworks imput file

## input files and starting the calculation

The FEM-model is here defined with tree text files:  
- .fem: main file, in which the type of calculatoin, the geometry, the load and the boundary cnditions are definied
- two .inp: files, in which the node, the node constrains and the element information are externalized (files were read in the .fem-file); these files were used to get  morcompact and readable .fem-file  

All files must be in the same folder. The example files in the MOOLDE course are  
- 210610_KerbscheibeKomplett_lin.fem
- 210503_Kerbscheibe_GridElement.inp
- 210503_Kerbscheibe_SPC.inp



Classically, three different processes are defined in the FEM calculation process:
1. preprocessor (generating the .fem model): here, only the material and the Load has to be defined; this can be done with hymermesh or direct by editing the .fem-file
2. solver (calculation process): here, hte solver optistruct is used. The calculation can be startet in two different ways:
	- by clicking the analyse-button after the import of the .fem file in hyperworcs via *import, import solver deck*
	- By starting the calculation with the [command line](https://2021.help.altair.com/2021/hwsolvers/os/topics/solvers/os/run_optistruct_intro_r.htm), for ex. *C:\"Program Files"\Altair\2021.2\hwsolvers\scripts\optistruct 210610_KerbscheibeKomplett_lin.fem*
3. postprocessor: here, the result files are loded in hyperview and funny pictures can be created

Altair Hyperworks Online Help ([here the link to the 2021 version](https://2021.help.altair.com/2021/hwsolvers/os/topics/solvers/os/analysis_sub_r.htm) ), especially the reference guide $\rightarrow$ input data $\rightarrow$ bulk data seciont

## input file structure

The description is only given here for the parts of the input file which need to be edited.

The first section in the input file is the subcase information section. The calculatoin type and the Load and boundary conditions are definied here.

```
ANALYSIS STATICS
  SPC = 2
  LOAD = 11
```

In this case a linear calculation (*ANALYSIS STATICS*) is defined, using the boundaries with the id *2* (Single Poit Constraint) and the Load with the id *11*.

In the bulk data section the elemet properties are definied.

```
PSHELL,1,1,1.0,,,,,0.0

```

In the example the properties for shell elements are given. The meaning of the numbers after the Keyword *PSHELL* are described [here](https://2021.help.altair.com/2021/hwsolvers/os/topics/solvers/os/pshell_bulk_r.htm).

A linear elastic material is defined using the keyword *MAT1*, a orthotropic linear elastic material is defined using *MAT8*. 

````
MAT1,1,70000.,,0.33,7.85-9
MAT8,2,120000.,8000.,0.32,3200.
````

The direction of the orthotropic mterial is defined with a special coordinat system. The coordinate system is assigned to the elements in the element definition (see *.210503_Kerbscheibe_GridElement.inp*)

````
CORD2R,44,0,0.0,0.0,0.0,0.0,0.0,1.0
,1.0,1.0,0.0
````

In the example fem-file the load can be applied as a constraint by *SPCD*

```
SPCD,21,9999,2,1.0
```

or as a force by *FORCE*

```
FORCE,11,9999,0,1.0,0.0,10000.,0.0
$$=== constraint at the node for load application
SPC,2,9999,1345,0.0
```
