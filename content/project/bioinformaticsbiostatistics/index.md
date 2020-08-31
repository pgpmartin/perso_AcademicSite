---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Bioinformatics and Biostatistics"
summary: "Tools for the analysis and integration of high throughput data"
authors: []
tags: ["genomics", "bioinformatics", "biostatistics", "data integration", "NGS"]
categories: ["bioinfo"]
date: 2020-08-30T22:57:36-04:00

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Bioinformatics & Biostatistics"
  focal_point: "Center"
  preview_only: false

# Custom links (optional).
#   Uncomment and edit lines below to show custom links.
# links:
# - name: Follow
#   url: https://twitter.com
#   icon_pack: fab
#   icon: twitter

url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""

#Optional header
header:
  image: "headers/BioinfoBiostat_bandeau.png"
  caption: "Bioinfo & Biostats"

---

 While developing transcriptomic approaches during my PhD, I quickly felt the need to learn more tools from biostatistics in order to perform thorough analyses of my data.  
  
  I quickly initiated a sustained collaboration with mathematicians from [Toulouse Math Institute](https://www.math.univ-toulouse.fr), in particular:  
  
  * [Sébastien Déjean](https://perso.math.univ-toulouse.fr/dejean/)  
  * [Philippe Besse](https://www.math.univ-toulouse.fr/~besse/index.html)  
  * [Alain Baccini](https://www.math.univ-toulouse.fr/~baccini/).  

  &nbsp;&nbsp;&nbsp;&nbsp;We first made an inventory of methods relevant to analyze transcriptomic data ([Baccini *et al.*, 2005]({{< relref "publication/2005_JStatFR/index.md" >}})).  
  In order to integrate transcriptomic and lipidomic data acquired during my PhD, Igniacio Gonzalez developed the regularized version of Canonical Correlation Analysis ([Gonzalez *et al.*, 2008]({{< relref "publication/2008-01-17_CCApackage/index.md" >}})).  
  This initial work was then taken in multiple directions by [Kim-Anh Lê Cao](http://lecao-lab.science.unimelb.edu.au/) who developed the first version of the [mixomics](http://mixomics.org/) package during her PhD (see for example [Lê Cao *et al.*, 2009]({{< relref "publication/2009-03-17_19171069/index.md" >}})) and still actively leads the development of this package and of data integration methods.  
  
  With Sébastien Déjean, we also developed methods to analyze transcriptomic data acquired during time-series experiments ([Déjean *et al.*, 2010]({{< relref "publication/2010-06-28_17713590/index.md" >}})).
  
  This experience in biostatistics was extensively used in my research projects. Notably I developed a pipeline for the analysis of microarray data that is still the foundation of the statistical analyses performed by the [GeT-TRiX](https://www6.toulouse.inra.fr/toxalim/Plateformes-Technologiques/E23-TRiX) transcriptomic facility.  
  
  Since 2015, I have gained more experience in bioinformatics for the analysis of next-generation sequencing (NGS) data, in particular using [R](http://www.r-project.org) and [Bioconductor](http://bioconductor.org/).  
  I have developed my first R package named [GeneNeighborhood](https://github.com/pgpmartin/GeneNeighborhood). It allows to explore the orientation and proximity of the direct upstream and downstream neighbors of a predefined set of genes.  
  I have also developed the [NanoBAC](https://github.com/pgpmartin/NanoBAC) R package and a [snakemake](https://snakemake.readthedocs.io/en/stable/) pipeline to assemble the reads obtained from BAC sequencing on the Oxford Nanopore long read sequencers. 
  
  
