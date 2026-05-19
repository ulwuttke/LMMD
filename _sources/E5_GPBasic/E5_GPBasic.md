# Gnuplot Basics

## Introduction 

Script-based programming languages like [python](https://www.python.org/) or [R](https://www.r-project.org/) are recommended for analysing large volumes of data. Compared to ‘proper’ programming languages, these have the advantage that their command sets are relatively easy to implement. Although such scripts are initially more difficult to understand than programmes such as EXCEL, they enable more efficient work when dealing with complex applications, numerous repetitions or simply very large volumes of data.

Here, [Gnuplot](https://en.wikipedia.org/wiki/Gnuplot) is used. Compared to Python or R, Gnuplot is very limited and focuses primarily on the graphical representation of datasets. However, it has the same scripting command character, is easy to install on all platforms, and offers a manageable set of commands.

## First small Gnuplot script

Gnuplot can display the output directly on the screen or save it directly to a file in a variety of graphic formats. Therefore, the output need to be specified in the first line. Here, the “Windows terminal” (standard on Windows computers) is set. The second and third line begins with the comment symbol #, so these lines are ignored. If the #-symbol is erased, 
the output will be written in the file "test-plot.png".

```
set terminal windows mono
#set terminal png
#set output "test-plot.png"

```

Data is plottet by the following command where

- *using 1:2* means: the first column in the file are x-values, the 2nd column are the y-values.
- *every 2* means: plot only every second data point 
- *title* (or short *t*) defines a title
- *pt* and *ps* are modifiing the shape and size of the points

```
plot 'testdaten.dat' using 1:2 every 2 title'testdata' pt 6 ps 2
```

Copy these two code lines a new text file and saved as a **.plt** file.

To have some plotting data copy the following "random" x-y-values in a new text file and save it as *testdaten.dat*.

```
#testdata
# x-values	y1-values	y2-values
-2.10	0.39	10.33
-0.25	4.40	8.18
1.32	9.75	6.27
3.72	12.87	7.34
5.87	6.38	2.64
7.95	24.54	-0.478
9.71	39.36	-3.48
11.84	41.36	6.02
13.47	8.16	-8.31
15.24	17.78	-1.83
17.63	71.72	4.76
19.31	17.12	-2.76
21.86	91.64	-33.38
```

```{dropdown} If you now run the gnuplot-script, the plot should look like this:
![Testdaten-plot](test-plot.png)
```

To use the third column as y-values and every data point try

```
plot 'testdaten.dat' using 1:3 every 1 title'testdata' pt 6 ps 2
```
... or both data sets (with different pt and ps)
```
plot 'testdaten.dat' using 1:2 every 1 title'y1-testdata' pt 6 ps 2,\
'testdaten.dat' using 1:3 every 1 title'y2-testdata' pt 2 ps 4
```

... and with axis label and a defined range (to be inserted before the *plot*-command):

```
# axis label
set xlabel 'x-values'
set ylabel 'y-values'
#
set xrange[-5:25]
set yrange[-50:100]
set key bottom center
```

**NOTE** You get greek letters (here sigma) or symbols via *set label '{/Symbol s}'*  

## Modify data

There are some rudimental possibilities to modify the data in gnuplot. For example the values in the first column multiplied by a factor of 10 as x-values, and the square of the corresponding value in the second column as the y-value


```
plot 'testdaten.dat' using ($1*10):($2**2) every 1 title'mod-testdata' pt 6 ps 2
```

...or the first column as x-values and the sum of the corresponding values of the 2nd and 3rd column:

```
plot 'testdaten.dat' using ($1):($2+$3) every 1 title'mod-testdata' pt 6 ps 2
```

## *fit*-command or linear regression unsing gnuplot

The [FIT function](https://gnuplot.sourceforge.net/docs_4.2/node82.html) in gnuplot uses an algorithm to minimise the sum of the squares of the ‘vertical’, $y$ deviations of a choosen function and a set of data points by adjusting the function’s parameters accordingly (parameter fit or parameter optimisation). In the case of a linear function $f(x)=a\cdot x+b$ the algorithm is a [linear regression](https://en.wikipedia.org/wiki/Linear_regression). Here the fit-parameters are $a$ and $b$. Because the sum of the squares is the quantity being optimised, it is called 'least-squares fitting'.

To see the result try:

```
f(x)=a*x+b
fit f(x) 'testdaten.dat' using 1:2 via a,b
plot 'testdaten.dat' using ($1):($2) every 1 title'testdata' pt 6 ps 2,\
f(x)
print "a = ",a,"; b =",b 
```

the output should be like this

```{dropdown} ... the output schould be like this:
![Fit-plot](fit-plot.png)
```

Please note: The 'print' command is a line output in the gnuplot-shell. In the working directory a file called "fit.log" schould appear. In this file internal fit-data and the values for the parameters $a$ and $b$ are documented.

The quantification of how good the curve fit on the x-y-data-points can be be done by calculating the [coefficient of determinatioin](https://en.wikipedia.org/wiki/Coefficient_of_determination). This can be done in gnupot by al little trick:
The *coefficient of determination* is defined as

[$R^2=1-\frac{SS_{res}}{SS_{tot}}$](https://en.wikipedia.org/wiki/Coefficient_of_determination#Definitions)

with the

- residual sum of squares: $SS_{res}$ or $SSR$ (or in german:  Summe Quadrate Residuen $SQR$) and the
- total sum of squares: $SS_{tot}$ or $SST$ (or in german:  Summe Quadrate Total $SQT$) 

The residual sum of squares $SSR$ is calculated by gnuplot in the fit-process and stored in the variamle FIT_WSSR. The value of the total sum of squares $SST$ has to be calculatet in a seperat fit.  
[The total sum of squares is the sum of the deviation of each y-value to the mean value of all y-values](https://commons.wikimedia.org/wiki/File:Coefficient_of_Determination.svg#/media/File:Coefficient_of_Determination.svg). The mean value can be calculated in gnuplot by fitting a constant function $g(x)=c$. The mean-y-value is $c$, the value of the total sum of squares $SST$ is now stored in the variable FIT_WSSR. So $R^2$ can be calculated:

```
f(x)=a*x+b
fit f(x) 'testdaten.dat' using 1:2 via a,b
SSR=FIT_WSSR
g(x)=c
fit g(x) 'testdaten.dat' using 1:2 via c
SST=FIT_WSSR
R2=1.-SSR/SST
plot 'testdaten.dat' using ($1):($2) every 1 title'testdata' pt 6 ps 2,\
f(x) title'linear fit'
set print 'results.txt'
print "a = ",a,"; b =",b,"; c =",c ,"; R^2 =",R2
set print 
``` 

In this case the print-output is printed in the file *results.txt* in the *append*-mode, which means, that if the file already exists, new data will be added.

