## Resources

- [RNA-seq Bioinformatics](https://rnabio.org/)

 
## Transcriptome

- [De novo transcriptome assembly](https://angus.readthedocs.io/en/2019/transcriptome-assembly-nematostella.html)
- [Annotating and evaluating a de novo transcriptome assembly](https://angus.readthedocs.io/en/2019/dammit_annotation.html)
- [Evaluating your transcriptome assembly](https://dibsi-rnaseq.readthedocs.io/en/latest/evaluation.html)

- [RNA-seq Analysis](https://angus.readthedocs.io/en/2019/RNA-seq-Analysis.html)
- [RNA-seq read quantification with salmon](https://angus.readthedocs.io/en/2019/salmon-quant.html)
- [Differential Expression and Visualization in R](https://angus.readthedocs.io/en/2019/diff-ex-and-viz.html)

## Workflows

- [**Differential Gene Expression using RNA-Seq (Workflow)**](https://github.com/twbattaglia/RNAseq-workflow)

- [Snakemake workflow: rna-seq-star-deseq2](https://github.com/snakemake-workflows/rna-seq-star-deseq2)
- [**RNA-seq workflow: gene-level exploratory analysis and differential expression**](https://bioconductor.org/packages/release/workflows/vignettes/rnaseqGene/inst/doc/rnaseqGene.html)


## Tutorials

- [人人都要会的转录组(RNA-seq)下游分析](https://zhuanlan.zhihu.com/p/77901431)
- [**Analyzing RNA-seq data with DESeq2**](http://bioconductor.org/packages/devel/bioc/vignettes/DESeq2/inst/doc/DESeq2.html)
- [DESeq2差异基因分析和批次效应移除](https://mp.weixin.qq.com/s?__biz=MzI5MTcwNjA4NQ==&mid=2247485368&idx=1&sn=12b20487e9014ce2e69f01d3efbc6ce8&chksm=ec0dc232db7a4b248530e117a86053a9149d9ede5258326e04a4ab375f6858853c2e4c06d07d&scene=21#wechat_redirect)


## Tools

- [List of RNA-Seq bioinformatics tools](https://en.wikipedia.org/wiki/List_of_RNA-Seq_bioinformatics_tools)

QC

- [SortMeRNA](https://github.com/biocore/sortmerna/)

Quantification

- [**Salmon**](https://salmon.readthedocs.io/en/latest/salmon.html) - a tool for wicked-fast transcript quantification from RNA-seq data

Assembly

- [stringtie](https://github.com/gpertea/stringtie) - Transcript assembly and quantification for RNA-Seq


Count data handling

- [tximport](https://github.com/mikelove/tximport) - Import and summarize transcript-level estimates for transcript- and gene-level analysis
    - [Importing transcript abundance with tximport](http://bioconductor.org/packages/release/bioc/vignettes/tximport/inst/doc/tximport.html)
- [tximeta](https://github.com/mikelove/tximeta) - Transcript Quantification Import with Automatic Metadata
    - [Tximeta: transcript quantification import with automatic metadata](https://bioconductor.org/packages/release/bioc/vignettes/tximeta/inst/doc/tximeta.html)
- [TxDb.Hsapiens.UCSC.hg19.knownGene](https://bioconductor.org/packages/release/data/annotation/html/TxDb.Hsapiens.UCSC.hg19.knownGene.html)

Explore

- [ReportingTools](http://bioconductor.org/packages/release/bioc/html/ReportingTools.html) - Tools for making reports in various formats
- [pcaExplorer](http://bioconductor.org/packages/release/bioc/html/pcaExplorer.html) -an R/Bioconductor package for interacting with RNA-seq principal components, [doc](http://bioconductor.org/packages/release/bioc/vignettes/pcaExplorer/inst/doc/upandrunning.html)

Pathway Database

- [ReactomePA](https://bioconductor.org/packages/release/bioc/html/ReactomePA.html) - provides functions for pathway analysis based on REACTOME pathway database. It implements enrichment analysis, gene set enrichment analysis and several functions for visualization.

Enrichment Analysis

- [clusterProfiler](http://yulab-smu.top/clusterProfiler-book/) - universal enrichment tool for functional and comparative study

Resource

- [MSigDB](https://www.gsea-msigdb.org/gsea/msigdb/index.jsp) (human only),
  for human and mouse: [MSigDF](https://github.com/ToledoEM/msigdf), mouse: [GSKB](https://bioconductor.org/packages/release/data/experiment/html/gskb.html)
- [MeSH](https://meshb.nlm.nih.gov/)
- [AnnotationHub](https://bioconductor.org/packages/devel/bioc/vignettes/AnnotationHub/inst/doc/AnnotationHub.html) - Access the AnnotationHub Web Service
- [org.Hs.eg.db](https://bioconductor.org/packages/release/data/annotation/html/org.Hs.eg.db.html)
- [org.Mm.eg.db](https://bioconductor.org/packages/release/data/annotation/html/org.Mm.eg.db.html)
- [org.Rn.eg.db](https://bioconductor.org/packages/release/data/annotation/html/org.Rn.eg.db.html)
- [MeSH.Hsa.eg.db](https://bioconductor.org/packages/release/data/annotation/html/MeSH.Hsa.eg.db.html)
- [MeSH.Mmu.eg.db](https://bioconductor.org/packages/release/data/annotation/html/MeSH.Mmu.eg.db.html)
- [MeSH.Rno.eg.db](https://bioconductor.org/packages/release/data/annotation/html/MeSH.Rno.eg.db.html)

Online tools

- [idep](http://bioinformatics.sdstate.edu/idep/) - an integrated web application for differential expression and pathway analysis of RNA-Seq data
