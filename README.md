# Reanalysis of CHISEL single-cell copy-number data

## Overview

This project explores whether simple statistical analysis of processed single-cell DNA copy-number data can recover tumour clone structure reported by CHISEL.

CHISEL infers allele- and haplotype-specific copy-number states from single-cell DNA sequencing and uses these profiles to investigate intra-tumour heterogeneity.

I reanalysed processed data from patient S0, tumour section E.

## Question
To what extent can simple PCA and hierarchical clustering of copy-number profiles reproduce the tumour clone structure reported by CHISEL?

## Data 
The analysis used publicly available processed CHISEL outputs.

The dataset contained 2,075 cells. 1,448 of these had published assignments to six tumour clones. Copy-number profiles covered 570 genomic regions.

## Analysis
Total copy number was calculated from the two haplotype-specific copy numbers for each genomic region.

The analysis included:
-genome-wide copy-number visualisation
-PCA of total copy number
-Ward hierarchical clustering
-comparison with published clone assignments using adjusted Rand index
-PCA and clustering using allele-specific copy numbers

## Results
Simple total-copy-number analysis recovered substantial published clone structure.

The first two total-copy-number principal components explained 91.9% and 3.7% of variance, respectively.

Ward hierarchical clustering achieved an adjusted Rand index of 0.792 relative to the published CHISEL clone assignments.

Some clones were recovered particularly clearly, including Clone5 and Clone63. However, total-copy-number clustering merged Clone156 and Clone172.

Retaining allele-specific copy numbers revealed additional separation between Clone156 and Clone172 in PCA. However, overall hierarchical clustering agreement was essentially unchanged (ARI = 0.791)

## Limitations
This project begins with copy-number states inferred by CHISEL rather than raw sequencing reads. Therefore, it does not independently validate CHISEL's copy-number inference.

Only one patient section was analysed.

The diploid-reference alteration metric treats total copy number two as baseline and therefore requires caution in genomes with altered ploidy.

Simple PCA and Ward clustering do not reproduce the specialised statistical and evolutionary modelling performed by CHISEL.

## Purpose
This repository is an independent educational reanalysis of publicly available processed data. It is not original research and is not an attempted reimplementation of CHISEL.