---
title: Blastn output format 6
author: Pascal
date: '2021-03-12'
slug: blastn-output-format-6
categories:
  - bioinfo
tags:
  - bioinformatics
  - alignment
subtitle: ''
summary: ''
authors: []
lastmod: '2021-03-12T12:04:14+01:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---



**See also:**  

 - [Blast documentation](https://www.ncbi.nlm.nih.gov/books/NBK279690/pdf/Bookshelf_NBK279690.pdf)
 - [Blast on Metagenomics Wiki](http://www.metagenomics.wiki/tools/blast/blastn-output-format-6)
 - `blastn -help` and check `-outfmt` formatting option

## Prepare the database
Only needed if reference sequences are going to be used frequently

```bash
makeblastdb \
  -in myRefSeqs.fasta \
  -out "My/Folder/myRefSeqs_blastdb" \
  -dbtype "nucl" \
  --parse_seqids \
  -logfile My/Folder/logFile.log
```

## Run Blast
`-num_alignment` default is `250`. Modify it if more alignments are expected  
`-outfmt` sets the output format  

```bash
blastn \
  -task megablast \
  -query InputSequence.fasta \
  -db "My/Folder/myRefSeqss_blastdb" \
  -out My/Output/Folder/InputSeq_vs_RefSeqs.res \
  -outfmt 6 \
  -num_alignments 10000000
```

Run blast with 2 fasta sequences:
```bash
blastn \
  -query genes.fasta \
  -subject genome.fasta \
  -outfmt 6
```

Default value for `-outfmt 6` corresponds to `-outfmt "6 qseqid sseqid pident length mismatch gapopen qstart qend sstart send evalue bitscore"`

## Output

Column headers:  
<span style="color:blue">`qseqid sseqid pident length mismatch gapopen qstart qend sstart send evalue bitscore` </span>  
In R:  
```r
c("qseqid","sseqid", "pident", "length", 
  "mismatch", "gapopen", "qstart", "qend", 
  "sstart", "send", "evalue", "bitscore")
```

|Col | name    | Description |
| --:| :-----    |:------------------
| 1. | <span style="color:blue">qseqid</span>    | query (e.g., unknown gene) sequence id |
| 2. | <span style="color:blue">sseqid</span>    | subject (e.g., reference genome) sequence id |
| 3. | <span style="color:blue">pident</span>    | percentage of identical matches |
| 4. | <span style="color:blue">length</span>    | alignment length (sequence overlap) |
| 5. | <span style="color:blue">mismatch</span>  | number of mismatches |
| 6. | <span style="color:blue">gapopen</span>   | number of gap openings |
| 7. | <span style="color:blue">qstart</span>    | start of alignment in query |
| 8. | <span style="color:blue">qend</span>      | end of alignment in query |
| 9. | <span style="color:blue">sstart</span>    | start of alignment in subject |
| 10. | <span style="color:blue">send</span>     | end of alignment in subject |
| 11. | <span style="color:blue">evalue</span>   | expect value |
| 12. | <span style="color:blue">bitscore</span> | bit score |

