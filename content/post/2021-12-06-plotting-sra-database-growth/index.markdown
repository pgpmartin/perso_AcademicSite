---
title: Plotting SRA database growth
author: Pascal
date: '2021-12-06'
slug: plotting-sra-database-growth
categories:
  - bioinfo
  - genomics
tags:
  - bioinformatics
  - genomics
subtitle: ''
summary: ''
authors: []
lastmod: '2021-12-06T15:00:47+01:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---

The [Sequence Read Archive](https://www.ncbi.nlm.nih.gov/sra/) is NCBI's database for high throughput sequencing data and the largest public repository for such data.  
The data on the growth of the database is available [here](https://www.ncbi.nlm.nih.gov/sra/docs/sragrowth/)

## Load packages

```r
suppressPackageStartupMessages(library(magrittr))
suppressPackageStartupMessages(library(httr))
suppressPackageStartupMessages(library(ggplot2))
```

## Function to make nicer axis labels

```r
scientific_10 <- function(x) {
  xx <- dplyr::case_when(x>=0 & x<=100 ~ as.character(x),
                         x>100 & log10(x)%%1==0 ~ gsub(".+e\\+", "10^", scales::scientific_format()(x)),
                         TRUE ~ gsub("e\\+", " %*% 10^", scales::scientific_format()(x))) 
  parse(text = xx)
}
```


## Download the data in  R

```r
sraurl <- "https://www.ncbi.nlm.nih.gov/Traces/sra/sra_stat.cgi"

sra <- httr::GET(url=sraurl) %>% 
        httr::content(encoding="UTF-8")

sra$date <- as.Date(sra$date, format = "%m/%d/%Y")
```

## Plot with linear scale

```r
sra %>%
  dplyr::select(date, bases, open_access_bases) %>%
  tidyr::pivot_longer(cols = 2:3, names_to = "type", values_to = "terabases") %>%
  dplyr::mutate(terabases = terabases / 1e12) %>%
  dplyr::mutate(type = dplyr::case_when(type == "bases" ~ "total bases",
                                 type == "open_access_bases" ~ "open access bases")) %>%
ggplot(mapping = aes(x = date, y = terabases, color = type)) +
  geom_line(size = 1.5) +
  scale_color_manual(name = NULL,
                     values = c("total bases" = "darkred",
                                "open access bases" = "darkblue")) +
  scale_y_continuous(labels = scientific_10 ) +
  labs(x = "Year", y = expression( Terabases~(10^12) ),
       title = "Growth of Sequence Read Archive database") +
  theme_bw() +
  NULL
```

<img src="{{< blogdown/postref >}}index_files/figure-html/sra_plot_linear_scale-1.png" width="672" />


## Plot with log scale

```r
sra %>%
  dplyr::select(date, bases, open_access_bases) %>%
  tidyr::pivot_longer(cols = 2:3, names_to = "type", values_to = "bases") %>%
  dplyr::mutate(type = dplyr::case_when(type == "bases" ~ "total bases",
                                 type == "open_access_bases" ~ "open access bases")) %>%
ggplot(mapping = aes(x = date, y = bases, color = type)) + 
  geom_line(size = 1.5) + 
  scale_color_manual(name = NULL,
                     values = c("total bases" = "darkblue",
                                "open access bases" = "darkred")) +
  scale_y_log10(labels = scientific_10 ) +
  labs(x = "Year", y = "bases" ,
       title = "Growth of Sequence Read Archive database") +
  theme_bw() +
  NULL
```

<img src="{{< blogdown/postref >}}index_files/figure-html/sra_plot_log_scale-1.png" width="672" />

