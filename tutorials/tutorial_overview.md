GenAp2 single-cell tutorials overview
================
Florian Wuennemann

# Introduction

Welcome to the tutorial pages for the single-cell RNA-seq data
processing pipelines implemented in GenAP2. We aim to support a broad
range of different users and therefore implemented a number of different
starting points for using our pipelines.

If you are interested in the details and setup of the entire processing
pipeline, please consult the following manual page:

[Pipeline description](./pipeline_description.md)

If you want to process your scRNA-seq data, choose your starting point
and follow the instructions to analyze your data. For all starting
points, you can either run an entire pipeline that will at the end
format your data to be analyzed using our custom GenAP2 shiny apps, or
you can just use each tool individually and continue processing on your
own with your favourite tools. Full pipeline workflows are marked
**full\_pipe** while workflows for only running the tool are labeled
**tool\_only**.

[I have raw FASTQ files for my samples](#part1)

[I have a DGE file (matrix of cells x genes) containing UMI counts form
10x CellRanger](#part2)

[I have a processed Seurat object (Seurat v2.3.4)](#part3)

# I have raw FASTQ files for my samples

If you are starting off with raw FASTQ files for your samples, choose
one of the pipeline presented here. At the moment, we provide one tool
to quantify FASTQ files, which is salmon-alevin. In the current
iteration, this tool can quantify FASTQ files from the following
technologies: \* Drop-seq \* 10x v2 chemistry \* 10x v3 chemistry

To start with this tutorial, upload your .gz or .fastq files to your
galaxy instance. If you don’t know how to upload data, please follow
[these instructions](#Upload_files).

Once youre files are uploaded, select one of the following workflows. We
are currently providing the transcriptome references for Human
(H.sapiens, Gencode v29, ) and Mouse (M.musculus,Gencode VM20, )

  - **alevin\_seurat\_shiny** : This workflow will run salmon alevin to
    map, quantify and assign your reads from .fastq files. It will
    afterwards run Seurat (v2.3.0) to cluster and annotate cells and
    then format the seurat output for visualization in the GenAP2 Rshiny
    app.

  - **alevin\_scanpy\_shiny** : This workflow will run salmon alevin to
    map, quantify and assign your reads from .fastq files. It will
    afterwards run Scanpy (1.4.2) to cluster and annotate cells and then
    format the seurat output for visualization in the GenAP2 Rshiny app.

  - **alevin\_only** : This workflow will only run salmon alevin on your
    file to map, quantify and assign your reads from your fast file. If
    you want to use the sparseMatrix downstream, just save it from the
    galaxy as .rds file and load it into
R\!

# I have a DGE file (matrix of cells x genes) containing UMI counts form 10x CellRanger

If you have data that has been processed using 10x CellRannger software
and you want to use either Seurat or Scanpy to analyze the data and then
visualize is in shiny, use one of the following workflows:

  - **10x\_seurat\_shiny** : This workflow will run Seurat (v2.3.0) on
    your 10x data to cluster and annotate cells and then format the
    seurat output for visualization in the GenAP2 Rshiny app.

  - **10x\_scanpy\_shiny** : This workflow will run salmon alevin to
    map, quantify and assign your reads from .fastq files. It will
    afterwards run Scanpy (1.4.2) to cluster and annotate cells and then
    format the seurat output for visualization in the GenAP2 Rshiny app.

Otherwise, you can also run either of these complete tools by using the
**seurat\_only** or **scanpy\_only** workflows. The Seurat workflow will
return a .Rds object that contains clustering information in tSNE space
and a marker list. The Scanpy workflow will return an anndata object
with clustering information and a marker list.

# I have a processed Seurat object (Seurat v2.3.4)

If you have already analyzed your data using Seurat v2.3.4 and have an
annotated .rds object with tSNE mappings, use the following workflow:

**format\_seurat\_for\_shiny** : This tool will take a fully clustered
Seurat .rds object alongside a marker list from Seurats `FindAllMarker`
function as input and reformat this data for visualization using the
GenAP2 app.

# How to upload files to your Galaxy instance

# Acknowledgements

![](../www/canarie-logo.png)

This project was funded by [Canarie Inc. (Ottawa,
Canada)](https://www.canarie.ca/) under the grant: Research Software
Program Funding Call \# 2b – RS-311.

![](../www/genap_logo.png)

The pipelines are all integrated into the existing GenAP2 framework,
which has been established by the GenAP2 team.
