Details about the computational pipelines
================

# Pipeline description

We have set up several popular scRNA-seq tools inside the GenAP2 galaxy
framework. We are planning to implement more tools in the future. Check
back at the [GenAP homepage](https://genap.ca/public/home) frequently to
find out about any new tools implemented.

All of the code for these tools is available freely on Github under the
. Please note that the galaxy tool implementations for Seurat and Scanpy
have been developed by the [EBI Gene Expression
Group](https://github.com/ebi-gene-expression-group) and have only been
forked and tested in the GenAP2 galaxy implementation.

## Currently implemented tools

### Alignment and quantification of scRNA-seq data

These tools allow you to directly input raw FASTQ files to quantify your
single-cell data.

**[Salmon Alevin](https://combine-lab.github.io/alevin-tutorial/#blog)**

  - Github : <https://github.com/FloWuenne/salmon_alevin>
  - Supports Drop-seq, 10x v2 and 10x v3 input formats
  - Fast, quasi-mapping approach for scRNA-seq quantification

### Clustering and analysis of scRNA-seq

These are tools that usually take a Digital expression matrix (DGE) as
input and perform dimensional reduction on your scRNA-seq data.

**[Seurat v2.3.4 (galaxy tool by EBI gene expression
group)](https://satijalab.org/seurat/v2.4/pbmc3k_tutorial.html)**

  - Github :
    <https://github.com/FloWuenne/genap2_ebi_scRNAseq_tools/tree/master/seurat>
  - Currently only v2.3.4 is supported, meaning SCT normalization is not
    yet possible inside galaxy
  - Very popular scRNA-seq analysis toolkit in R by the Satija lab

[Scanpy v.1.3.2 (galaxy tool by EBI gene expression
group)](https://scanpy.readthedocs.io/en/stable/)

  - Github :
    <https://github.com/FloWuenne/genap2_ebi_scRNAseq_tools/tree/master/scanpy>
  - Python-based analysis toolkit for single-cell expression data by the
    Theis lab

### Visualization and annotation of scRNA-seq results

**[scCluster-annotate](https://github.com/FloWuenne/scCluster_genap2)**

  - Github : <https://github.com/FloWuenne/scCluster_genap2>
  - Rshiny based app that allows users to easily and quickly visualize
    and anotate their single-cell RNA-seq data
