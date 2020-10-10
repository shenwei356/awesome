# R

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [Base](#base)
- [Tutorial ](#tutorial)
- [Packages](#packages)
- [Text](#text)
- [Performance](#performance)
- [Data wrangling](#data%C2%A0wrangling)
- [CLI](#cli)
- [ML](#ml)
- [Visualization](#visualization)
- [Color](#color)
- [Heatmap](#heatmap)
- [ggplot2](#ggplot2)
- [Statistics](#statistics)
- [Cluster](#cluster)
- [File formats](#file-formats)
- [Misc](#misc)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->


## Base

update all R packages

    install.packages("rvcheck")
    update_all()

install github repo

    library(devtools)
    devtools::install_github("kassambara/survminer")
    # if http error: manually download and install_url("file:///home/xxx/xx.tar.gz")
    
## Tutorial 

- [R for data science](https://github.com/hadley/r4ds)
- [**Cheatsheets by rstudio**](https://www.rstudio.com/resources/cheatsheets/) https://github.com/rstudio/cheatsheets
- [Hands-On Data Science with R](http://onepager.togaware.com/)
- [DataPyR](https://datapyr.zeef.com/kranthi.kumar)
- [http://www.sthda.com/english/](http://www.sthda.com/english/)
- [http://www.r-bloggers.com/search/ggplot2](http://www.r-bloggers.com/search/ggplot2)
- [**Mastering Software Development in R**](https://bookdown.org/rdpeng/RProgDA/)

## Packages

- [10 R packages I wish I knew about earlier](http://blog.yhathq.com/posts/10-R-packages-I-wish-I-knew-about-earlier.html)
- [Great R packages for data import, wrangling & visualization](http://www.computerworld.com/article/2921176/business-intelligence/great-r-packages-for-data-import-wrangling-visualization.html)
- [R package development - the Leek group way! ](https://github.com/jtleek/rpackages)

## Text

- [stringr](https://github.com/tidyverse/stringr) - A fresh approach to string manipulation in R http://stringr.tidyverse.org
- [Text Processing in R](http://www.mjdenny.com/Text_Processing_In_R.html)
- [pystr](https://github.com/nicolewhite/pystr) - Python String Methods in R. [http://cran.r-project.org/web/packages/pystr](http://cran.r-project.org/web/packages/pystr)
- [R语言基础知识-字符串的处理](http://r.rzaixian.com/%E5%9F%BA%E6%9C%AC%E6%93%8D%E4%BD%9C/how-to-deal-with-string-huyuan.html)

## Performance

docs

- [http://rstatistics.net/strategies-to-speed-up-r-code/](http://rstatistics.net/strategies-to-speed-up-r-code/)
- [Quick Intro to Parallel Computing in R](https://nceas.github.io/oss-lessons/parallel-computing-in-r/parallel-computing-in-r.html)

packages

- [future](https://github.com/HenrikBengtsson/future) - R package: future: Unified Parallel and Distributed Processing in R for Everyone
- [furrr](https://davisvaughan.github.io/furrr/) - simplify the combination of purrr’s family of mapping functions and future’s parallel processing capabilities.


## Install

```
> devtools::install_github("houyunhuang/ggcor")
Error in curl::curl_fetch_memory(url, handle = h) 
error setting certificate verify locations:
CAfile: /opt/microsoft/ropen/3.5.2/lib64/R/lib/microsoft-r-cacert.pem 
CApath: none
```

One solution :

    remove.packages(c("curl","httr"))
    install.packages(c("curl", "httr"))

    file.edit('~/.Renviron')
    CURL_CA_BUNDLE=/usr/lib/R/lib/microsoft-r-cacert.pem


## Data wrangling

io

- [data.table](https://github.com/Rdatatable/data.table)
- [readr](https://readr.tidyverse.org/) 


data structure

- [tibble](http://tibble.tidyverse.org/) - A tibble, or tbl_df, is a modern reimagining of the data.frame, keeping what time has proven to be effective, and throwing out what is not.

tools

- [tidyverse](www.tidyverse.org) 
- [tidytidbits](https://cran.r-project.org/web/packages/tidytidbits/index.html) A selection of various tools to extend a data analysis workflow based on the 'tidyverse' packages
- [faster-data-manipulation-7-packages](http://www.analyticsvidhya.com/blog/2015/12/faster-data-manipulation-7-packages/)
- [data-wrangling-cheatsheet.pdf](https://www.rstudio.com/wp-content/uploads/2015/02/data-wrangling-cheatsheet.pdf)
- [tidyr](https://github.com/hadley/tidyr) tidyr is a reframing of reshape2 designed to accompany the tidy data framework, and to work hand-in-hand with magrittr and dplyr to build a solid pipeline for data analysis.
- [dplyr-and-plyr](http://www.slideshare.net/Sheffield_R_/dplyr-and-plyr), [When I use plyr/dplyr](http://educate-r.org//2014/01/24/usePlyr/)，[Using dplyr, and a comparison with plyr.]http://scicomp2014.edc.uri.edu/posts/2014-04-14-Smith.html
- [dplyr: How to do data manipulation with R](http://www.sharpsightlabs.com/dplyr-intro-data-manipulation-with-r/)
    - [Data Wrangling Part 1: Basic to Advanced Ways to Select Columns](https://suzan.rbind.io/2018/01/dplyr-tutorial-1/)
    - [Data Wrangling Part 2: Transforming your columns into the right shape](https://suzan.rbind.io/2018/02/dplyr-tutorial-2/)
- [Programming with dplyr](http://dplyr.tidyverse.org/articles/programming.html) 
- [normalising-data-within-groups](http://www.r-bloggers.com/normalising-data-within-groups/), [script](https://dl.dropboxusercontent.com/u/67041874/normalise.R)
- [**broom**](https://github.com/tidyverse/broom) - Convert Statistical Analysis Objects into Tidy Data Frames
- [widyr](https://github.com/dgrtwo/widyr) - Widen, process, and re-tidy a dataset


## CLI

- [argparse](https://cran.r-project.org/web/packages/argparse/)

## ML

docs

- [useR-machine-learning-tutorial](https://github.com/ledell/useR-machine-learning-tutorial/blob/master/random-forest.Rmd)

packages

- [caret](https://github.com/topepo/caret/) - (Classification And Regression Training) R package that contains misc functions for training and plotting classification and regression models https://topepo.github.io/caret/index.html
- [ROCR](https://rocr.bioinf.mpi-sb.mpg.de/) - visualizing classifier performance in R, with only 3 commands
- [xgboost](https://github.com/dmlc/xgboost) - Scalable, Portable and Distributed Gradient Boosting (GBDT, GBRT or GBM) Library, for Python, R, Java, Scala, C++ and more. Runs on single machine, Hadoop, Spark, Flink and DataFlow
    - [How to use XGBoost algorithm in R in easy steps](https://www.analyticsvidhya.com/blog/2016/01/xgboost-algorithm-easy-steps/)

## Visualization

- Large number of images: [http://rgm3.lab.nig.ac.jp/RGM/R_image_list](http://rgm3.lab.nig.ac.jp/RGM/R_image_list)
- [Static and dynamic network visualization with R](http://kateto.net/network-visualization)
- [http://rcharts.io/gallery/](http://rcharts.io/gallery/)
- [corrplot](https://cran.r-project.org/web/packages/corrplot/vignettes/corrplot-intro.html)
- ordination plots
- Dendrogram: hclust
- [factoextra](https://github.com/kassambara/factoextra) -  Visualization of the outputs of a multivariate analysis [http://www.sthda.com](http://www.sthda.com/)
- Sankey from Scratch using rCharts, d3.js, and igraph
- [largevis](https://github.com/elbamos/largevis) - This is an implementation of the largeVis algorithm described in (https://arxiv.org/abs/1602.00370). It also incorporates code for a very fast algorithm for estimating k-nearest neighbors.
- [Vennerable](https://github.com/js229/Vennerable) - Vennerable provides Venn diagrams in R. It displays Venn and Euler diagrams for up to 9 different sets and using a variety of geometries. It allows the display of area-weighted Venn diagrams and allows fine graphical control over the result.
- [alluvial](https://github.com/mbojan/alluvial) - Alluvial diagrams (you can also use [ggalluvial](https://github.com/corybrunson/ggalluvial)
- [UpSetR](https://github.com/hms-dbmi/UpSetR) - An R implementation of the UpSet set visualization technique published by Lex, Gehlenborg, et al..
- [ggcorrplot](https://github.com/kassambara/ggcorrplot) - Visualization of a correlation matrix using ggplot2 https://rpkgs.datanovia.com/ggcorrplot/


book

- [Fundamentals of Data Visualization](http://serialmentor.com/dataviz/)

misc

- [Mathematical Annotation in R](http://vis.supstat.com/2013/04/mathematical-annotation-in-r/)

circos like

- [rCircos](https://cran.r-project.org/web/packages/RCircos/index.html): R package for circular plots. [last update: 2013]
- [**OmicCircos**](http://www.bioconductor.org/packages/release/bioc/html/OmicCircos.html): R package for circular plots for omics data. [vignette](http://www.bioconductor.org/packages/release/bioc/vignettes/OmicCircos/inst/doc/OmicCircos_vignette.pdf) [last update: 2016-05]
- [**circlize**](https://github.com/jokergoo/circlize) - circular layout in R http://jokergoo.github.io/circlize

graph

- [Network Visualizations in R using ggraph and graphlayouts](http://mr.schochastics.net/netVizR.html)
- [Network visualization with R](https://kateto.net/network-visualization)
- [igraph](http://igraph.org/r/), [**Network Analysis and Visualization with R and igraph**](http://kateto.net/networks-r-igraph)
- [**ggraph**](https://github.com/thomasp85/ggraph) - Grammar of Graph Graphics
- [ggnetwork](https://github.com/briatte/ggnetwork)
- [ggnet](https://github.com/briatte/ggnet) - Simple network plots with ggplot2 in R.

Shiny

- [Building Web Data Products with R & Shiny](https://www.codementor.io/r/tutorial/building-a-web-based-sentiment-classifier-using-r-shiny)

- [shinyWidgets](https://github.com/dreamRs/shinyWidgets) - shinyWidgets : Extend widgets available in shiny 

## Color

- [R color cheatsheet](https://www.nceas.ucsb.edu/~frazier/RSpatialGuides/colorPaletteCheatsheet.pdf)
- [RColorBrewer](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&ved=0CB8QFjAAahUKEwic7ene6uTGAhXPMIgKHbSBAvs&url=http%3A%2F%2Fcran.r-project.org%2Fpackage%3DRColorBrewer&ei=DVuqVdyyHc_hoAS0g4rYDw&usg=AFQjCNHdzsnSUdQ4Uj7y4721JA426mW_dA&sig2=p6oVhW7jglAJcQRPNQI_HA)


## Heatmap

- ComplexHeatmap
- [pheatmap](http://www.inside-r.org/packages/cran/pheatmap/docs/pheatmap)

## ggplot2


Extended packages. More: [RStartHere](https://github.com/rstudio/RStartHere#visualize),
[ggally](https://github.com/ggobi/ggally)

[ggplot2 extensions - gallery](https://exts.ggplot2.tidyverse.org/gallery/)

- [esquisse](https://github.com/dreamRs/esquisse) - RStudio add-in to make plots with ggplot2 

- [***ggthemes***](https://cran.r-project.org/web/packages/ggthemes/vignettes/ggthemes.html) - Some extra themes, geoms, and scales for  ggplot2.
- [hrbrthemes](https://github.com/hrbrmstr/hrbrthemes) - Opinionated, typographic-centric ggplot2 themes and theme components
- [**ggcharts**](https://thomas-neitmann.github.io/ggcharts/index.html) - provides a high-level ggplot2 interface for creating common charts.
- [**ggsci**](https://cran.r-project.org/web/packages/ggsci/vignettes/ggsci.html) - Scientific Journal and Sci-Fi Themed Color Palettes for ggplot2
- [***cowplot***](https://github.com/wilkelab/cowplot)  - provide a publication-ready theme for ggplot2. similar package: [ggmatrix](https://ggobi.github.io/ggally/gh-pages/ggmatrix.html), [ggpairs](https://ggobi.github.io/ggally/gh-pages/ggpairs.html), [ggscatmat](https://ggobi.github.io/ggally/gh-pages/ggscatmat.html)
- [***ggfortify***](https://github.com/sinhrks/ggfortify) - Define fortify and autoplot functions to allow ggplot2 to handle some popular R packages.  [http://cos.name/2015/11/ggfortify-visualization-in-one-line-of-code/](http://cos.name/2015/11/ggfortify-visualization-in-one-line-of-code/)
- [***ggrepel***](https://github.com/slowkow/ggrepel) - Repel overlapping text labels away from each other.
- [***ggalt***](https://github.com/hrbrmstr/ggalt) - Extra Coordinate Systems, Geoms and Statistical Transformations for 'ggplot2' https://cran.rstudio.com/web/packages/ggalt/ggalt.pdf
- [***ggforce***](https://github.com/thomasp85/ggforce) - aime primarily at ad hoc data visualization in order to investigate the data at hand, and less at utilities for composing custom plots a la D3.js.
- [sina plot](https://cran.r-project.org/web/packages/sinaplot/vignettes/SinaPlot.html): `geom_sina`:  enhanced jitter strip char
- [***gganimate***](https://github.com/dgrtwo/gganimate) - Create easy animations with ggplot2
- [ggord](https://github.com/fawda123/ggord) - a take on ordination plots using ggplot2
- [gbiplot](https://github.com/vqv/ggbiplot) - A biplot based on ggplot2
- [ggvis](http://ggvis.rstudio.com/)- Interactive grammar of graphics for R
- [***ggcorr***](https://briatte.github.io/ggcorr/): correlation matrixes with ggplot2
- [***ggtree***](http://guangchuangyu.github.io/ggtree): an R package for visualization and annotation of phylogenetic trees with their covariates and other associated data.
- [***ggsurv***](https://ggobi.github.io/ggally/#ggallyggsurv) - survival curves with ggplot2
- [ggExtra](https://github.com/daattali/ggExtra) Add marginal histograms to ggplot2, and more ggplot2 enhancements http://daattali.com/shiny/ggExtra-ggMarginal-demo/
- [ggradar](https://github.com/ricardo-bion/ggradar) - radar charts with ggplot2
- [ggRandomForests](https://cran.r-project.org/web/packages/ggRandomForests/) : Visually Exploring Random Forests
- [ggmcmc](https://cran.r-project.org/web/packages/ggmcmc/index.html): Tools for Analyzing MCMC Simulations from Bayesian Inference
- [***ggalluvial***](https://github.com/corybrunson/ggalluvial) - alluvial diagrams in ggplot2
- [ggpubr](https://github.com/kassambara/ggpubr) - 'ggplot2' Based Publication Ready Plots
- [gggenes](https://github.com/wilkox/gggenes) - Draw gene arrow maps in ggplot2
- [ggfittext](https://github.com/wilkox/ggfittext) - ggplot2 geoms to fit text into boxes
- [**ggbeeswarm**](https://github.com/eclarke/ggbeeswarm) - Provides methods for beeswarm plots in ggplot2
- [gghighlight](https://github.com/yutannihilation/gghighlight/) - Highlight points and lines in ggplot2
- [**waffle**](https://github.com/hrbrmstr/waffle) - Make waffle (square pie) charts in R
  [introduction](https://nsaunders.wordpress.com/2017/09/08/infographic-style-charts-using-the-r-waffle-package/)
- [**ggridges**](https://github.com/clauswilke/ggridges) - Geoms to make ridgeline plots with ggplot2
- [ggwrap](https://github.com/wilkox/ggwrap) - ‘ggwrap’ wraps a ‘ggplot2’ plot over multiple rows, to make plots with long x axes easier to read.
- [ggbump](https://github.com/davidsjoberg/ggbump) - A geom for ggplot to create bump plots
- [ggdag](https://ggdag.malco.io/) - An R Package for visualizing and analyzing causal directed acyclic graphs
- [ggpol](https://erocoar.github.io/ggpol/)
- [gghalves](https://github.com/erocoar/gghalves) - Easy half-half geoms in ggplot2 https://erocoar.github.io/gghalves/
- [sugrrants](https://pkg.earo.me/sugrrants/) - Calendar-based graphics
- [lindia](https://github.com/yeukyul/lindia) - Extension package of linear regression diagonostic plots in ggplot2.
- [ggnewscale](https://github.com/eliocamp/ggnewscale) - Multiple Fill and Color Scales in `ggplot2`
- [ggrastr](https://github.com/VPetukhov/ggrastr) - Provides a set of ggplot2 geoms to rasterize only specific layers of the plot 

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
- [R语言：ggplot2精细化绘图——以实用商业化图表绘图为例](http://www.cnblogs.com/weibaar/p/4567791.html)
- [The Evolution of a ggplot (Ep. 1)](https://cedricscherer.netlify.app/2019/05/17/the-evolution-of-a-ggplot-ep.-1/)

## Statistics

book

- [Summary and Analysis of Extension Program Evaluation in R](http://rcompanion.org/handbook/)

misc

- [**Quick Multivariate data analysis (PCA, CA, MCA) and visualization**](http://www.sthda.com/english/wiki/factoextra-r-package-quick-multivariate-data-analysis-pca-ca-mca-and-visualization-r-software-and-data-mining)
- [The R Stats Package](https://stat.ethz.ch/R-manual/R-devel/library/stats/html/00Index.html) ([Adjust P-values for Multiple Comparisons](http://stat.ethz.ch/R-manual/R-devel/library/stats/html/p.adjust.html), [多重检验中的FDR错误控制方法与p-value的校正及Bonferroni校正](http://fhqdddddd.blog.163.com/blog/static/18699154201093171158444/))
- [How can I do post-hoc pairwise comparisons in R?](https://stats.idre.ucla.edu/r/faq/how-can-i-do-post-hoc-pairwise-comparisons-in-r/)

- [Kruskal–Wallis Test](http://rcompanion.org/handbook/F_08.html)
- [Multiple Comparison Procedures](http://www.jerrydallal.com/lhsp/mc.htm)

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


## Bioinformatics

### batch effect

- [sva](https://bioconductor.org/packages/release/bioc/html/sva.html) - Surrogate Variable Analysis, contains functions for removing batch effects and other unwanted variation in high-throughput experiment. 


### ID mapping

- [biomaRt](https://bioconductor.org/packages/release/bioc/html/biomaRt.html)

### xxx

- [plyranges](https://github.com/sa-lee/plyranges) - A grammar of genomic data transformation https://sa-lee.github.io/plyranges/

## GLM

- [glmnet](https://cran.r-project.org/web/packages/glmnet/index.html)
- [eNetXplorer](https://cran.r-project.org/web/packages/eNetXplorer/index.html)

### Enrichment Analysis

- [clusterProfiler](https://yulab-smu.github.io/clusterProfiler-book)

Dataset

- [rWikiPathways](https://bioconductor.org/packages/release/bioc/html/rWikiPathways.html)
- [msigdbr](https://cran.r-project.org/web/packages/msigdbr/index.html)
- [NCG](http://ncg.kcl.ac.uk/) Cancer Genes
- [ReactomePA](https://bioconductor.org/packages/release/bioc/html/ReactomePA.html) Reactome Pathway Analysis

### Survival Analysis

[Cox Proportional-Hazards Model](http://www.sthda.com/english/wiki/cox-proportional-hazards-model)

- [survival](https://cran.r-project.org/package=survival)
- [survminer](https://rpkgs.datanovia.com/survminer/)
- [survcomp](http://www.bioconductor.org/packages/release/bioc/html/survcomp.html)
- [survivalAnalysis](https://cran.r-project.org/web/packages/survivalAnalysis/) - A high-level interface to perform survival analysis, including Kaplan-Meier analysis and log-rank tests and Cox regression

### TCGA

- [TCGAmutations](https://github.com/PoisonAlien/TCGAmutations)
- [CDGS-R](https://www.cbioportal.org/rmatlab)
- [xena](https://xenabrowser.net/datapages/)
- [UCSCXenaTools](https://github.com/ShixiangWang/UCSCXenaTools), [intro]https://shixiangwang.github.io/home/en/post/ucscxenatools-201908/)

### Ecology

- [vegan](https://github.com/vegandevs/vegan) R package for community ecologists: popular ordination methods, ecological null models & diversity analysis https://CRAN.R-project.org/package=vegan
