My R learning note.

## R

configurations

```
$ vim ~/.Rprofile
# http not https!!!
options(repos=c(CRAN="http://mirrors.tuna.tsinghua.edu.cn/CRAN/"))
options(BioC_mirror="http://mirrors.tuna.tsinghua.edu.cn/bioconductor")

utils::setRepositories(ind=1:2)

```


update all installed packages:

```R
library(rvcheck)
update_all()
```


## Basic

- R −−max−mem−size =1Gb
- `options(digits =2 )`
- Data type
    - 字符(charactor)    它们常常被引号包围
    - 数字(numeric)      实数向量
    - 整数(integer)      整数向量
    - 逻辑(logical)      逻辑向量( TRUE=T、 FALSE=F)
    - 复数(complex)      复数a
    - 列表(list)         S 对象的向量
    - 因子(factor )      常用于标记样本
- 1 e10 == 10000000000
- `x[!is.na(x)]`

## string

split string

```
groups <- unlist(strsplit(args$groups, ","))
```

regular expression capture

```R
> library(stringr)
> s <- "_A_123_B_"
> found <- str_match(s, "A(.+)B")
> found
     [,1]      [,2]   
[1,] "A_123_B" "_123_"
> found[,2]
[1] "_123_"

# str_match_all() to match all groups in a regex
```

## Data Structures

### Vector

```R
v <- seq(1, 10, 2) # 1 3 5 7 9
> c(1,2,c(3:5))
[1] 1 2 3 4 5
len <- length(v) # 5
c(v[1:2], 4, v[3:5]) # add an element
y <- vector(length=10) #
for (i in seq(v) ) print(i) # seq(1, length(v))
> rep(1:3, 2)
[1] 1 2 3 1 2 3
> rep(1:3, each=2)
[1] 1 1 2 2 3 3
> any(-1:1 > 0)
[1] TRUE

# filter
> v <- c(1, 2, NA, 3, 4)
> v[v>2]
[1] NA  3  4
> subset(v, v>2)
[1] 3 4
> ifelse(is.na(v), 0, v)
[1] 1 2 0 3 4

all(x==y) # exactly equal
```

### Matrix and Array

```R
nrow, ncol for array. NROW NCOL　for vector
> a = array(1:6, c(3,2))
> a
     [,1] [,2]
[1,]    1    4
[2,]    2    5
[3,]    3    6
> apply(a, 1, mean)
[1] 2.5 3.5 4.5
> apply(a, 2, mean)
[1] 2 5
> a = matrix(1:6, nrow=3)
> a
     [,1] [,2]
[1,]    1    4
[2,]    2    5
[3,]    3    6
> a[,2]
[1] 4 5 6
> a[,2, drop=FALSE]  # avoid dimension reduction
     [,1]
[1,]    4
[2,]    5
[3,]    6
> colnames(a) <- c("a", "b")
> rownames(a) <- c("r1", "r2", "r3")
> a
   a b
r1 1 4
r2 2 5
r3 3 6
> a[,'b']
r1 r2 r3
 4  5  6
#  apply function over each matrix element
> outer(1:nrow(mat), 1:ncol(mat) , FUN="*")
     [,1] [,2] [,3]
[1,]    1    2    3
[2,]    2    4    6
[3,]    3    6    9
[4,]    4    8   12
[5,]    5   10   15

> outer(1:nrow(mat), 1:ncol(mat) , FUN=function(r,c) log(r+c) )
          [,1]     [,2]     [,3]
[1,] 0.6931472 1.098612 1.386294
[2,] 1.0986123 1.386294 1.609438
[3,] 1.3862944 1.609438 1.791759
[4,] 1.6094379 1.791759 1.945910
[5,] 1.7917595 1.945910 2.079442
```

### List

```R
> l <- list("a"=1, "b"=2)
> l
$a
[1] 1

$b
[1] 2

> l["a"]
$a
[1] 1

> l[["a"]]
[1] 1
> l$a
[1] 1
>l$c <- 4 # new element
>unlist(l)
a b c
1 2 4
> lapply(list(1:3, 5:7), mean)
[[1]]
[1] 2

[[2]]
[1] 6
> sapply(list(1:3, 5:7), mean)
[1] 2 6

# filter list
> columns <- columns[sapply(columns, function(x) unlist(strsplit(as.character(x), ".", fix=TRUE))[1] %in% groups)]

```

### Data frame
```R
> df <- data.frame(id=c('a','b','c'),value=c(1,2,3))
> df
id value
1 a 1
2 b 2
3 c 3
> str(df)
'data.frame':   3 obs. of  2 variables:
 $ id   : Factor w/ 3 levels "a","b","c": 1 2 3
 $ value: num  1 2 3
> df[df$value>1,]
  id value
2  b     2
3  c     3
> subset(df, value>1)
  id value
2  b     2
3  c     3
> x <- df[, c("item", "rank")]
> library(dplyr)
> filter(df, value>1)
  id value
1  b     2
2  c     3
df < df[complete.cases(df),] #
merge(d1, d3, by.x="a", by.y="a") # merge

# filter by row sum
df2 <- df2[sapply(1:nrow(df2), function(i){sum(df[i, 2:nrow(df2)])>0}) > 0, ]
subSet <- DF[apply(DF,1,function(x){sum(tail(x,-1) >= 0.01) >= 2}),]
subSet <- DF[rowSums(DF[,2:ncol(DF)] >= 0.01) >= 2,]
```
sort

```R
x <- x[order(-x$rank),]
```

fill na

```R
x$rank[is.na(x$rank)] <- 0
```

replace text in data frame

```R
re <- function(x) {
  if (is.character(x) | is.factor(x)) {
    x <- gsub("dataset_","",x)
    x <- gsub(".fa","",x)
  }
  return(x)
}
df <- as.data.frame(lapply(df, re))
```

replace value to another

```
df %>% mutate(a=replace(a, a==0, NA))
```

remove columns

```R
Data$genome <- NULL  # single column

Data[1:2] <- list(NULL)  # remove multiple columns
Data[1:2] <- NULL        # does not work!

Data <- subset( Data, select = -a ) # other way
Data <- subset( Data, select = -c(d, b ) )
Data <- subset( Data, select = -c( d : b )
```

filter by colum names

```R
library(dplyr)

ext_tracks %>%
  select(storm_name, latitude, longitude, starts_with("radius_34"))
# starts_with(), ends_with(), contains(), matches
```


normalising-data-within-groups

```R
df %>%
  group_by(group) %>%
  mutate(value = count / sum(count)
```

another cool usage

mutate function

```R
# speedup relative to CPU=1
func <- function(app, time){
  i <- app[app=1] # time of CPU==1
  return(round(time[i]/time, 1))
}
df <- df  %>%
  group_by(test, dataset) %>%
  mutate(speedup=func(app, time_mean))

```


separate

```R

# mutate
# A.1 -> new gruop A
get_group <- function(sample) {
  return (unlist(strsplit(as.character(sample), ".", fixed = TRUE))[1])
}
mutate(group=get_group(x))

# separate (tidyr)
separate(col, c("group", "id"), seq = ".", remove = TRUE)

```

```
remember `group_by` before `mutate` and `summarise`:

```R
df.country.award <- df.best %>%
  group_by(region) %>%
  mutate(sum = length(award2)) %>%
  group_by(region, country, sum) %>%
  summarise(num = length(award2)) %>%
  group_by(region, country) %>%
  mutate(perc = round(num / sum, digits = 2))
```

sort

```
msleep %>%
  mutate(brainwt2 = ifelse(brainwt > 4, NA, brainwt)) %>%
  select(starts_with("brain")) %>%
  arrange(desc(brainwt))
```

[Inserting a new row to data frame for each group id](https://stackoverflow.com/questions/41350950/inserting-a-new-row-to-data-frame-for-each-group-id)

```R
library(dplyr)

df <- df %>%
    group_by(sample) %>%
    mutate(taxon = "Others", value = 100-sum(value)) %>%
    bind_rows(df, .) %>%
    arrange(sample) %>%
    unique()
```

### Others

- `list <- seq(1, 10, 0.1)`
- `repeat = rep(list, 5),  repeat2 = rep(x, each=5)`
- `y <- x[-1] except for 1`
- `digits <- as.character(z),  d <- as.integer(digits)`

hashmap

```R
g <- as.list(levels(factor(df$group)))
g.index <- seq(1,length(g))
names(g.index) <- g

Control   GROUP  GROUP2 
      1       2       3 

```

### parallel



```
library(parallel)

options("mc.cores"=detectCores())

mclapply

library(foreach)
foreach (i=1:3) %do% {
  sqrt(i)
}

library(foreach)
library(doParallel)
registerDoParallel(numCores)  # use multicore, set to the number of our cores
foreach (i=1:3) %dopar% {
  sqrt(i)
}


```

### plyr and dplyr
```R
df = data.frame(group=c('g1','g2','g1','g2'), id=c(1, 2, 3, 4), value=c(1, 2, 4, 6))
  group id value
1    g1  1     1
2    g2  2     2
3    g1  3     4
4    g2  4     6
```

summary of some columns (plyr)

```R
> ddply(df, .(group), summarise, mean=mean(value))
  group mean
1    g1  2.5
2    g2  4.0
> ddply(df, ~ group, summarise, mean=mean(value))
  group mean
1    g1  2.5
2    g2  4.0
> ddply(df, .(group, id), summarise, mean=mean(value), sd=sd(value), N=length(value), se=sd/sqrt(N))
  group id mean
1    g1  1    1
2    g1  3    4
3    g2  2    2
4    g2  4    6
```

reference column by index

```R
x <- df %>%
  mutate(a = .[[3]], b = .[[5]]) %>%
  group_by(item) %>%
  mutate(rank = get.rank(item, diff, p.corrected, a, b ))
```

## Google’ R Style Guide

- `variable.name` is preferred, `variableName`  is accepted
- FunctionName: `CalculateAvgClicks`  Make function names verb
- space: `if (debug)`, `x[1, ]`
- Curly Braces
R
```
if (is.null(ylim)) {
  ylim <- c(0, 0.06)
} else {

}
```
- Use <-, not =, for assignment.
- General Layout and Ordering

```R
Copyright statement comment
Author comment
File description comment, including purpose of program, inputs, and outputs
source() and library() statements
Function definitions
Executed statements, if applicable (e.g., print, plot)
```

- The possibilities for creating errors when using attach are numerous. Avoid it.
- Use S3 objects and methods unless there is a strong reason to use S4 objects or methods.

## Change order of factor
```R
# keep order
df_m$variable <- factor(df_m$variable, levels=unique(df_m$variable), ordered=TRUE)
```

```R
# Change the order of levels
sizes <- factor(sizes, levels = c("small", "medium", "large"))
```

```R
# change the order of levels in a factor based on values in the data
iss$spray <- reorder(iss$spray, iss$count, FUN=mean)
```

```R
# change the names of levels in a factor.
# Can also use quotes -- useful if there are spaces or other strange characters
revalue(sizes, c("small"="S", "medium"="M", "large"="L"))
# mapvalues() lets you use two separate vectors instead of a named vector
mapvalues(sizes, c("small", "medium", "large"), c("S", "M", "L"))
```

## Colors

[format your axis tick labels with commas](http://stackoverflow.com/questions/11610377/how-do-i-change-the-formatting-of-numbers-on-an-axis-with-ggplot)

cycle palette

```R
library(ggthemes)
library(scales)

colors <- stata_pal(scheme = "s2color")(15)
show_col(colors)

n <- 18 # give me 18 colors
show_col(rep(colors, ceiling(n/length(colors)))[1:n])
```

reverse gradient color

```R
library(RColorBrewer)
scale_fill_distiller(palette ="RdBu", direction = -1) # or direction=1
```


## ggplot

### theme

http://docs.ggplot2.org/dev/vignettes/themes.html


### axis

10,000

```R
library(scales)
scale_x_continuous(breaks = seq(0, max(df$loc), by = args$x_interval), labels = comma)
```

20%

```R
library(scales)
scale_y_continuous(formatter = 'percent')
```

log

```R
library(scales)
p + scale_x_log10(breaks=10^(-1:5),
　　　　　labels=trans_format("log10", math_format(10^.x))) +
　　scale_y_log10(breaks=10^(0:3),
　　　　　labels=trans_format("log10", math_format(10^.x)))
```

10^n

```

# https://github.com/jpshanno/ecoflux/blob/master/R/Helper_Functions.R#L379
scientific_10x <- function(values, digits = 1) {
  if(!is.numeric(values)){
    stop("values must be numbers")
  }
  if(grepl("^\\d{2}$", digits)){
    stop("digits must a one or two digit whole number")
  }
  
  x <- sprintf(paste0("%.", digits, "e"), values)
  
  x <- gsub("^(.*)e", "'\\1'e", x)
  
  longestExponent <- max(sapply(gregexpr("\\d{1,}$", x), attr, 'match.length'))
  zeroTrimmed <- ifelse(longestExponent > 2,
                        paste0("\\1", paste(rep("~", times = longestExponent-1), collapse = "")),
                        "\\1")
  x <- gsub("(e[+|-])[0]", zeroTrimmed, x)
  
  x <- gsub("e", "~x~10^", x)
  
  if(any(grepl("\\^\\-", x))){
    x <- gsub("\\^\\+", "\\^~~", x)
  } else {
    x <- gsub("\\^\\+", "\\^", x)
  }
  # return this as an expression
  parse(text=x)
} 
```

## plot differently in facets

```R
ann_text <- data.frame(strain =c("△mutL", "PAO1::sacB"), 
                       count_mean = c(1000, 15),
                       count_se = c(0, 0),
                       type=c("brown", "brown")
                       )
 geom_text(data = ann_text,label = "ND") + 
```

## wrap facet strip text

```R
wrapit <- function(text) {
  wtext <- paste(strwrap(text,width=40),collapse=" \n ")
  return(wtext)
}

data$wrapped_text <- llply(data$text, wrapit)
data$wrapped_text <- unlist(data$wrapped_text)
```

## legend

[wrap legend text](http://stackoverflow.com/questions/10332387/wrap-legend-text-in-ggplot2)

```R
library(scales)
i + guides(colour = guide_legend(nrow = 2))
```

disable some legend

```
guide(color=FALSE)
```

## plot

plot text in midle of every stacked bar 

```R
df.region.medal <- df.region.medal %>%
  group_by(region) %>%
  mutate(cnum = cumsum(num) - num / 2)

p.region.medal <-
  ggplot(df.region.medal, aes(x = region, y = num, fill = medal)) +
  geom_bar(stat = "identity") +
  geom_text(aes(y = cnum, label = lable )
```

[How can I combine multiple ggplot2 elements into the return of a function?
](https://stackoverflow.com/questions/4835332/how-can-i-combine-multiple-ggplot2-elements-into-the-return-of-a-function)

```
myFunction <- function()
 list(geom_vline(xintercept = 20),
      geom_point(data = mtcars))

p <- ggplot(aes(x = mpg, y = hp), data = mtcars)
p + myFunction()
```

## template

```R
#!/usr/bin/env Rscript
library(methods)
library(proto)

library(argparse)
library(dplyr)

library(ggplot2)

library(tidyr) # library(reshape2)

parser <- ArgumentParser(description = "", formatter_class = "argparse.RawTextHelpFormatter")

parser$add_argument("infile", type = "character", help = "")
parser$add_argument(
  "--width", type = "integer", default = 5,
  help = "output image width [20]"
)
parser$add_argument(
  "--ex", metavar = "ex", type = "double", default = 1.5,
  help = "x of equation [1.5]"
)
parser$add_argument("-s", "--gc-skew", action = "store_true",
                       dest = "gc_skew", help = "only plot GC Skew")

args <- parser$parse_args()

if (args$title == "") {
  args$title = NULL
}

#----------------------------------------------------------------

df <- read.csv(args[1], sep = "\t") # check.names=FALSE # avoid adding X

df <- select(df, X.chr, strand, cnt_f0, cnt_f1, cnt_f2)
df <- subset( df, select = c(-ID, -weight) )

df <- na.omit(df)

df$group <- factor(df$group, levels = unique(df$group), ordered = TRUE)


df <- df %>% gather(time, conc, -group, -a, convert = TRUE) # tidyr
# df <- df %>% gather(type, abundance, -1)
# df_m <- melt(df, id.vars = c("X.chr", "strand")) # reshape2 # not recommended


# mean and stdev
df2 <- df %>%
  group_by(type, group) %>%
  summarise(
    se = sd(conc) / sqrt(length(conc)),
    conc = mean(conc)
  )

  
#----------------------------------------------------------------

p <- ggplot(df_m) +

  geom_boxplot(aes(variable, value, fill = strand),
               position = position_dodge(width = 0.75)) +

  geom_bar(stat="identity", position="identity", colour="black", size=0.25) +
  # geom_bar(stat="identity", position="stack")+

  geom_text(aes(label=Weight), vjust=1.5, colour="white", position=position_dodge(.9), size=3) + # label
  geom_text(aes(y = cnum, label = ifelse(
    num > 1, sprintf("%d (%.0f%%)", num, perc * 100), ""
  )) # plot conditionally
  # label = sprintf("%0.2f", round(mean.value, digits = 2))  # sprintf
  # comma separated: format(size, big.mark=",",trim=TRUE)

  geom_line(aes(x=dose, y=length, linetype=supp), linetype="dashed", size=1, colour="blue") +

  geom_point(data = another.df, aes(variable, value, color=strand))+
  geom_point(size=4, shape=21, colour="darkred", fill="pink")
  geom_point(aes(x = group, y = count, colour = group, fill = group),
              position = position_jitterdodge(jitter.width=0.4,
                                              dodge.width=0.1)) +

  geom_vline(xintercept = markx_x2, colour="red")

  geom_hline(data=df2, aes(group = query, yintercept=mean),
              linetype=2, size=0.2)

  facet_grid(. ~ X.chr, scales = "free_y") +
  
  coord_flip() +

  scale_x_discrete(labels = c('0','1','2')) +
  scale_y_continuous(expand=c(0,0)) # delete space between bar and x axis
  scale_x_continuous(limits=c(0, args$x_limit), breaks = seq(0, args$x_limit, by = args$x_break))+
  scale_y_continuous(labels = comma) +  expand_limits(y=0) + # equal to ylim(0, max(BOD$demand))
  
  #  mix of plain and italic text in ggplot categorical x-axis
  scale_x_discrete(labels=c("strain",  expression(paste("Δ",italic("gene") )))) + 

  scale_fill_manual(values=c("#CCEEFF", "#FFDDDD"), guide=FALSE)
  

  xlab('Frame') +
  ylab('Counts') +
  ggtitle(args$title) +

  guides(fill = guide_legend(reverse = TRUE)) # reverse legend order, could not use color=**  in aes at the same time
  guides(fill = guide_legend(title="xxxx")) # change legend title
  labs(color="s...", shape="...")

p <- p +
  theme_bw() +
  theme(
    # backgroud
    panel.border = element_blank(),
    panel.background = element_blank(),
    # panel.grid = element_blank(),
    panel.grid.major = element_blank(),
    panel.grid.minor = element_blank(),

    # axis
    axis.line.x = element_line(colour = "black", size = 0.8),
    axis.line.y = element_line(colour = "black", size = 0.8),
    axis.text.x = element_blank(),
    axis.text.y = element_blank(),
    axis.ticks.x = element_blank(),
    axis.ticks.y = element_blank(),

    # border
    # panel.border = element_rect(colour = "black", size = 1.2, fill="transparent"),
    # axis.line.x = element_blank(),
    # axis.line.y = element_blank()

    # axis.ticks.y = element_blank(),
    # axis.title = element_blank(),
    # axis.text.x = element_text(angle=30, hjust=1, vjust=1)

    # remove y axix
    #     axis.line = element_line(colour = "black"),
    #     axis.line.y = element_line(colour = "white"),
    #     axis.ticks.y = element_blank(),
    #     axis.text.y = element_blank(),

    # legend
    legend.key = element_blank(),  
    legend.key.size = unit(0.3, "cm"),
    legend.spacing.x = unit(0.2, "cm"), # space between key and text
    legend.title = element_blank(),
    legend.text=element_text(size=12),  
    # legend.position = "none", # remove legend
    # legend.position = c(0.3, 0.2), # custom relative positon
    # 
    # legend.margin = unit(0.1, "cm"),
    legend.key.height=unit(1,"line"),
    legend.key.width=unit(1,"line"),

    # legend.background = element_rect(fill=alpha('blue', 0)), # need library(scale)    
    plot <- plot + theme(legend.position=c(1,1),legend.justification=c(1,1),
                       legend.direction="vertical",
                       legend.box="horizontal",
                       legend.box.just = c("top"),
                       legend.background = element_rect(fill="transparent"))

    # facet_grid
    strip.background = element_rect(
      colour = "white", fill = "white",
      size = 0.2
    )
    # remove strip
    #   strip.background = element_blank(),
    #   strip.text.x = element_blank(),
    #   strip.text.y = element_blank(),
    
    #   strip.text.x = element_text(angle = 0, hjust = 0), # left align
    strip.text.x = element_text(size = 12),
    strip.text.y = element_text(size = 12),

    text=element_text(size=12, family="arial", face="bold"),
    
    
    plot.margin = unit(c(0.1,0.1,0.1,0),"cm"),

    plot.title = element_text(size=16)
    # plot.title = element_text(hjust = 5)
  )

ggsave(p, file = paste(args$datafile, ".elisa.png", sep = ""),  
        width = 8, height = 4)
```

## template 2

```R

library(png)
library(grid)
library(ggplot2)
library(scales)
library(cowplot)
library(ggthemes)
library(ggrepel)


shenwei356.theme <-  theme_bw() +
  theme(
    panel.border = element_blank(),
    panel.background = element_blank(),
    panel.grid.major = element_blank(),
    panel.grid.minor = element_blank(),
    axis.line.x = element_line(colour = "black", size = 0.8),
    axis.line.y = element_line(colour = "black", size = 0.8),
    axis.ticks.x = element_line(size = 0.8),
    axis.ticks.y = element_line(size = 0.8),
    #     axis.text.x = element_text(
    #       angle = 30, hjust = 1, vjust = 1
    #     ),
    
    legend.key = element_blank(),
    legend.title = element_blank(),
    legend.text = element_text(size = 12, face = "plain"),
    legend.background = element_rect(fill = "transparent"),
    strip.background = element_rect(
      colour = "white", fill = "white",
      size = 0.2
    ),
    strip.text.x = element_text(size = 14),
    strip.text.y = element_text(size = 14),
    
    text = element_text(
      size = 14, family = "arial", face = "bold"
    ),
    plot.title = element_text(
      size = 16, family = "arial", face = "bold"
    )
  )

blank_theme <- theme(
  axis.title.x = element_blank(),
  axis.title.y = element_blank(),
  axis.text.x = element_blank(),
  axis.text.y = element_blank(),
  axis.ticks = element_blank(),
  panel.grid = element_blank(),
  axis.line = element_blank(),
  panel.background = element_blank(),
  plot.background = element_blank(),
  text = element_text(
    size = 14, family = "arial", face = "bold"
  ),
  plot.title = element_text(
    size = 18, family = "arial", face = "bold"
  )
)

plot_png <- function (file, title=NULL) {
  g <- rasterGrob(readPNG(file), interpolate = TRUE)
  df <- data.frame(x = c(0,0.5),y = c(0,0.5))
  p<- ggplot(df, aes(x = x, y = y)) +
    xlim(0,1) +
    ylim(0,1) +
    ggtitle(title) +
    annotation_custom(
      g, xmin = -Inf, xmax = Inf, ymin = -Inf, ymax = Inf
    ) +
    blank_theme
}

p <- plot_grid(
  plot_png("t.png"),
  plot_png("t.png"),
　　ggdraw() + draw_label(" "),　# blank
  ncol = 1,
  nrow = 2,
  labels = c("A", "B"),
  rel_heights = c(1, 1)
)
 + draw_label(
    "http://shenwei.me" ,
    angle = 35,
    size = 60,
    alpha = .1
  )  # water mark
ggsave(
  p, file = "Figure 2.png", width = 8, height = 5, dpi = 600
)


```

## misc
recode a continuous variable to another variable
```
pg$wtclass <- cut(pg$weight, breaks = c(0, 5, 6, Inf))
```
