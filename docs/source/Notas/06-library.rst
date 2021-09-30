Librerias
===========

> getOption("defaultPackages");
[1] "datasets"  "utils"     "grDevices" "graphics"  "stats"     "methods"
> tablaR151<-read.table("clipboard",header=TRUE,dec=",",sep="\t")
> tablaR151;
  id var1 var2
1  a    l    z
2  b    l    z
3  c    l    z
4  d    l    z
5  e    l    z
6  f    m    z
7  g    m    d
8  h    n    d
9  i    n    d
> tablaR152<-read.table("clipboard",header=TRUE,dec=",",sep="\t")
> tablaR152;
  id glucemia
1 xx      1.0
2 yy      1.1
3 zz      1.2
4 ww      0.9
> roc(tablaR151);
Error in roc(tablaR151) : no se pudo encontrar la función "roc"
> lbrary(pROC);
Error in lbrary(pROC) : no se pudo encontrar la función "lbrary"
> library(pROC);
Error in library(pROC) : there is no package called 'pROC'
> install.packages("pROC", dependencies=TRUE);
--- Please select a CRAN mirror for use in this session ---