# R

## base

update all R packages

    path <- "/home/shenwei/R/x86_64-redhat-linux-gnu-library/3.2"
    package_df <- as.data.frame(installed.packages(path))
    package_list <- as.character(package_df$Package) 
    install.packages(package_list)

## Tutorial 

- [Cheatsheets by rstudio](https://www.rstudio.com/resources/cheatsheets/)
- [Hands-On Data Science with R](http://onepager.togaware.com/)
- [DataPyR](https://datapyr.zeef.com/kranthi.kumar)
- [http://www.sthda.com/english/](http://www.sthda.com/english/)
- [http://www.r-bloggers.com/search/ggplot2](http://www.r-bloggers.com/search/ggplot2)

## Packages

- [10 R packages I wish I knew about earlier](http://blog.yhathq.com/posts/10-R-packages-I-wish-I-knew-about-earlier.html)
- [Great R packages for data import, wrangling & visualization](http://www.computerworld.com/article/2921176/business-intelligence/great-r-packages-for-data-import-wrangling-visualization.html)

## Text

- [Text Processing in R](http://www.mjdenny.com/Text_Processing_In_R.html)
- [pystr](https://github.com/nicolewhite/pystr) - Python String Methods in R. [http://cran.r-project.org/web/packages/pystr](http://cran.r-project.org/web/packages/pystr)
- [R语言基础知识-字符串的处理](http://r.rzaixian.com/%E5%9F%BA%E6%9C%AC%E6%93%8D%E4%BD%9C/how-to-deal-with-string-huyuan.html)

## Performance

- [http://rstatistics.net/strategies-to-speed-up-r-code/](http://rstatistics.net/strategies-to-speed-up-r-code/)

## Data wrangling

- [faster-data-manipulation-7-packages](http://www.analyticsvidhya.com/blog/2015/12/faster-data-manipulation-7-packages/)
- [data-wrangling-cheatsheet.pdf](https://www.rstudio.com/wp-content/uploads/2015/02/data-wrangling-cheatsheet.pdf)
- [tidyr](https://github.com/hadley/tidyr) tidyr is a reframing of reshape2 designed to accompany the tidy data framework, and to work hand-in-hand with magrittr and dplyr to build a solid pipeline for data analysis.
- [dplyr-and-plyr](http://www.slideshare.net/Sheffield_R_/dplyr-and-plyr), [When I use plyr/dplyr](http://educate-r.org//2014/01/24/usePlyr/)，[Using dplyr, and a comparison with plyr.]http://scicomp2014.edc.uri.edu/posts/2014-04-14-Smith.html
- [dplyr: How to do data manipulation with R](http://www.sharpsightlabs.com/dplyr-intro-data-manipulation-with-r/)
- [normalising-data-within-groups](http://www.r-bloggers.com/normalising-data-within-groups/), [script](https://dl.dropboxusercontent.com/u/67041874/normalise.R)

## CLI

- [argparse](https://cran.r-project.org/web/packages/argparse/)

## ML

- [caret](https://github.com/topepo/caret/) - (Classification And Regression Training) R package that contains misc functions for training and plotting classification and regression models
- [ROCR](https://rocr.bioinf.mpi-sb.mpg.de/) - visualizing classifier performance in R, with only 3 commands

## Visualization

- Large number of images: [http://rgm3.lab.nig.ac.jp/RGM/R_image_list](http://rgm3.lab.nig.ac.jp/RGM/R_image_list)
- [Static and dynamic network visualization with R](http://kateto.net/network-visualization)
- [http://rcharts.io/gallery/](http://rcharts.io/gallery/)
- corrplot
- ordination plots
- [igraph](http://igraph.org/r/), [**Network Analysis and Visualization with R and igraph**](http://kateto.net/networks-r-igraph)
- Dendrogram: hclust
- [factoextra](https://github.com/kassambara/factoextra) -  Visualization of the outputs of a multivariate analysis [http://www.sthda.com](http://www.sthda.com/)
- Sankey from Scratch using rCharts, d3.js, and igraph
- [rCircos](https://cran.r-project.org/web/packages/RCircos/index.html): R package for circular plots. [last update: 2013]
- [**OmicCircos**](http://www.bioconductor.org/packages/release/bioc/html/OmicCircos.html): R package for circular plots for omics data.[last update: 2015-04]


Shiny

- [Building Web Data Products with R & Shiny](https://www.codementor.io/r/tutorial/building-a-web-based-sentiment-classifier-using-r-shiny)

## Color

- [R color cheatsheet](https://www.nceas.ucsb.edu/~frazier/RSpatialGuides/colorPaletteCheatsheet.pdf)
- [RColorBrewer](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&ved=0CB8QFjAAahUKEwic7ene6uTGAhXPMIgKHbSBAvs&url=http%3A%2F%2Fcran.r-project.org%2Fpackage%3DRColorBrewer&ei=DVuqVdyyHc_hoAS0g4rYDw&usg=AFQjCNHdzsnSUdQ4Uj7y4721JA426mW_dA&sig2=p6oVhW7jglAJcQRPNQI_HA)


## Heatmap

- ComplexHeatmap
- [pheatmap](http://www.inside-r.org/packages/cran/pheatmap/docs/pheatmap)

## ggplot2


Extended packages. More: [RStartHere](https://github.com/rstudio/RStartHere#visualize), 
[ggally](https://github.com/ggobi/ggally)

- [***ggthemes***](https://cran.r-project.org/web/packages/ggthemes/vignettes/ggthemes.html) - Some extra themes, geoms, and scales for  ggplot2.
- [***cowplot***](https://github.com/wilkelab/cowplot)  - provide a publication-ready theme for ggplot2. similar package: [ggmatrix](https://ggobi.github.io/ggally/gh-pages/ggmatrix.html), [ggpairs](https://ggobi.github.io/ggally/gh-pages/ggpairs.html), [ggscatmat](https://ggobi.github.io/ggally/gh-pages/ggscatmat.html)
- [***ggfortify***](https://github.com/sinhrks/ggfortify) - Define fortify and autoplot functions to allow ggplot2 to handle some popular R packages.  [http://cos.name/2015/11/ggfortify-visualization-in-one-line-of-code/](http://cos.name/2015/11/ggfortify-visualization-in-one-line-of-code/)
- [***ggrepel**](https://github.com/slowkow/ggrepel) - Repel overlapping text labels away from each other.
- [ggalt](https://github.com/hrbrmstr/ggalt) - Extra Coordinate Systems, Geoms and Statistical Transformations for 'ggplot2' https://cran.rstudio.com/web/packages/ggalt/ggalt.pdf
- [ggforce](https://github.com/thomasp85/ggforce) - aime primarily at ad hoc data visualization in order to investigate the data at hand, and less at utilities for composing custom plots a la D3.js.
- [***gganimate***](https://github.com/dgrtwo/gganimate) - Create easy animations with ggplot2
- [ggord](https://github.com/fawda123/ggord) - a take on ordination plots using ggplot2
- [gbiplot](https://github.com/vqv/ggbiplot) - A biplot based on ggplot2
- [***ggnet***](https://github.com/briatte/ggnet) - Simple network plots with ggplot2 in R. Similar packages: [ggnetworkmap](https://ggobi.github.io/ggally/gh-pages/ggnetworkmap.html), [ggraph](https://github.com/thomasp85/ggraph) - Grammar of Graph Graphics
- [ggvis](http://ggvis.rstudio.com/)- Interactive grammar of graphics for R
- [***ggcorr***](https://briatte.github.io/ggcorr/): correlation matrixes with ggplot2
- [***ggsurv***](https://ggobi.github.io/ggally/gh-pages/ggsurv.html) - survival curves with ggplot2
- [ggExtra](https://github.com/daattali/ggExtra) Add marginal histograms to ggplot2, and more ggplot2 enhancements http://daattali.com/shiny/ggExtra-ggMarginal-demo/
- [ggradar](https://github.com/ricardo-bion/ggradar) - radar charts with ggplot2
- [ggRandomForests](https://cran.r-project.org/web/packages/ggRandomForests/) : Visually Exploring Random Forests
- [ggmcmc](https://cran.r-project.org/web/packages/ggmcmc/index.html): Tools for Analyzing MCMC Simulations from Bayesian Inference


Tutorial

- [使用ggplot2画图](http://ygc.name/2014/05/11/use-ggplot2/) - YGC
- [ggplot2-cheatsheet](https://www.rstudio.com/wp-content/uploads/2015/03/ggplot2-cheatsheet.pdf)
- [Getting started with ggplot2](http://rpubs.com/hadley/ggplot-intro)
- [Beautiful plotting in R: A ggplot2 cheatsheet](http://zevross.com/blog/2014/08/04/beautiful-plotting-in-r-a-ggplot2-cheatsheet-3/)
- [Recreating a famous visualisation](https://biomickwatson.wordpress.com/2015/04/09/recreating-a-famous-visualisation/)
- [ http://stackoverflow.com/questions/14379737/how-can-i-make-xlab-and-ylab-visible-when-using-theme-wsj-ggthemes]( http://stackoverflow.com/questions/14379737/how-can-i-make-xlab-and-ylab-visible-when-using-theme-wsj-ggthemes)
- [How to format plots for publication using ggplot2 (with some help from Inkscape)](http://www.noamross.net/blog/2013/11/20/formatting-plots-for-pubs.html)
- [Remove grid and background from plot (ggplot2)](http://felixfan.github.io/rstudy/2013/11/27/ggplot2-remove-grid-background-margin/)
- [Colors](http://www.cookbook-r.com/Graphs/Colors_(ggplot2)/)
- [ggplot2 - Easy way to mix multiple graphs on the same page](http://www.sthda.com/english/wiki/ggplot2-easy-way-to-mix-multiple-graphs-on-the-same-page-r-software-and-data-visualization)
- [2D plot with histograms for each dimension](http://blog.mckuhn.de/2013/04/2d-plot-with-histograms-for-each.html)
- [R Recipe: Aligning Axes in ggplot2]( http://www.exegetic.biz/blog/2015/05/r-recipe-aligning-axes-in-ggplot2/)
- [making-faceted-heatmaps-with-ggplot2/](http://rud.is/b/2016/02/14/making-faceted-heatmaps-with-ggplot2/)

## Statistics

- [Quick Multivariate data analysis (PCA, CA, MCA) and visualization](http://www.sthda.com/english/wiki/factoextra-r-package-quick-multivariate-data-analysis-pca-ca-mca-and-visualization-r-software-and-data-mining)
- [The R Stats Package](https://stat.ethz.ch/R-manual/R-devel/library/stats/html/00Index.html) ([Adjust P-values for Multiple Comparisons](http://stat.ethz.ch/R-manual/R-devel/library/stats/html/p.adjust.html), [多重检验中的FDR错误控制方法与p-value的校正及Bonferroni校正](http://fhqdddddd.blog.163.com/blog/static/18699154201093171158444/))

## Cluster

- [A gentle introduction to cluster analysis using R](https://eight2late.wordpress.com/2015/07/22/a-gentle-introduction-to-cluster-analysis-using-r/)

## File formats

-  [rio](https://github.com/leeper/rio) - A Swiss-army knife for data I/O

reads xlsx/xls library(xslx)

```
data <- read.xlsx("datafile.xlsx", 1)
```

```
library(gdata)
# Read first sheet
data <- read.xls("datafile.xls")
```

## Misc

- [How to summarize data by group in R?]( http://stats.stackexchange.com/questions/8225/how-to-summarize-data-by-group-in-r)
- [Error in eval(expr, envir, enclos) : object &#8216;X' not found](https://groups.google.com/forum/#!topic/ggplot2/qVE6Uxd_IFQ/discussion) solution: `ggplot(..., **environment = environment()**)`
- [how to apply a function to every row of a matrix (or a data frame) in R](http://stackoverflow.com/questions/4236368/how-to-apply-a-function-to-every-row-of-a-matrix-or-a-data-frame-in-r)
- [How to apply function over each matrix element](http://stackoverflow.com/questions/7395397/how-to-apply-function-over-each-matrix-element)
- [How do I pass variables to a custom function in ddply?]( http://stackoverflow.com/questions/20845409/how-do-i-pass-variables-to-a-custom-function-in-ddply)
- [R-Transposing a data frame]( http://stackoverflow.com/questions/6778908/r-transposing-a-data-frame)
