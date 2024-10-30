---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "Endoreduplication in tomato fruit"
summary: "Gene expression regulation during endoreduplication in the pericarp of tomato fruit"
authors: []
tags: ["genomics", "transcription", "chromatin", "gene expression", "bioinformatics", "R", "fruit biology", "growth", "plant", "endoreduplication"]
categories: ["gene expression", "genomics"]
date: 2020-08-30T22:57:36-04:00

# Optional external URL for project (replaces project detail page).
external_link: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: "Tomato nucleosome"
  focal_point: "Center"
  preview_only: true

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

# Optional header
header:
  image: "headers/TomatoNucleosome_bandeau.png"
  caption: "Tomato nucleosome"

---

  Endoreduplication is a process by which cells replicate their DNA but do not divide. Successive rounds of this modified cell cycle, called the endocycle, generate polyploid cells with increasing numbers of copies of their genome.  

{{< figure library="true" src="endoreduplication_cycles.png" title="Cell cycle and endocycle" >}}  
*[CC BY 4.0](https://creativecommons.org/licenses/by/4.0)*

  Endoreduplication is a phenomenon that occurs in a wide range of animal species including mammals, insects and other metazoans and in different tissues. It also occurs in fungi but it is most widespread in plants, occurring in up to 90% of Angiosperms.  
  Early during tomato fruit development, cell divisions are replaced by endoreduplication, giving rise to progressively larger cells with ploidy levels up to 512C, that contribute to the growth and structure of the tissue.      

{{< figure library="true" src="Development_WVA106_winterculture.png" title="Endoreduplication in tomato fruit development" >}}  
  *Picture by Ulysse Tuquoi ([CC BY 4.0](https://creativecommons.org/licenses/by/4.0))*

  Endoreduplication contributes to cell growth and cell differentiation pathways and is sometimes activated in response to environmental cues in plants. Much work has been devoted to identify the pathways that control the endocycle. However, little is known about the gene regulations that are associated with endoreduplication and how chromatin structure and epigenetic marks are affected in highly polyploid cells.  
  
  Since 2021, I joined the [FDFE team](https://www6.bordeaux-aquitaine.inrae.fr/bfp_eng/Research/Team-Flowering-Fruit-Development-and-Environmental-Constraints-FDFE) that studies endoreduplication in tomato fruit.  

  Using a [cell sorter](https://en.wikipedia.org/wiki/Cell_sorting), it is possible to separate the nuclei of different ploidy levels (2C, 4C, 8C, etc.) from the pericarp (the fleshy part of the fruit) of tomato fruits. We used this technique to analyze by RNA-seq the transcriptome of cells from different ploidy levels and at different developmental stages. This allowed us to show that ploidy in itself plays an important role in shaping the transcriptome of cells in the pericarp [Tourdot *et al.*, 2024]({{< relref "publication/2024-05-10_38281284/index.md" >}}).  

  Based on this observation, we have proposed to investigate the epigenome of endoreduplicated cells and to evaluate if and how it is involved in regulating gene expression changes observed in polyploid cells. We are developing [ATAC-seq](https://en.wikipedia.org/wiki/ATAC-seq) and [CUT&RUN](https://en.wikipedia.org/wiki/CUT%26RUN_sequencing) / [CUT&TAG](https://en.wikipedia.org/wiki/CUT%26Tag_sequencing) protocols to investigate chromatin in polyploid nuclei from tomato fruit.  
  
  This work is funded by projects from INRAE pertament BAP, from Université de Bordeaux and from the ANR (TomEndCODE project).  
  
