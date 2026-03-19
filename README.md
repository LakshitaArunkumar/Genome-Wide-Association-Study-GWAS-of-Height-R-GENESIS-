## Genome-Wide Association Study (GWAS) of Height (R, GENESIS)

This project implements a genome-wide association study (GWAS) pipeline to identify genetic variants associated with height. The analysis integrates genotype data, phenotype information, population structure, and relatedness using linear mixed models in R.

---

## Project Overview

Height is a complex, quantitative trait influenced by both genetic and environmental factors. This project performs a GWAS using imputed genotype data to identify variants associated with height while accounting for population stratification and relatedness.

---

## Objectives

- Perform GWAS on a continuous phenotype (height)  
- Apply variant-level quality filtering  
- Adjust for population structure using principal components  
- Account for relatedness using a genetic relatedness matrix (GRM)  
- Identify significantly associated variants  

---

## Workflow Summary

### Data Exploration

- Loaded sample annotation data  
- Evaluated:
  - Sample size  
  - Phenotype distribution (height)  
  - Covariates (sex, population)  

- Assessed phenotype distribution using histograms and Q-Q plots  

---

### Variant Filtering

- Evaluated imputed genotype data using:
  - Imputation quality (r²)  
  - Allele frequency (AF)  

- Applied filters:
  - r² > 0.8  
  - 0.01 < AF < 0.99  

- Retained high-quality variants for downstream analysis  

---

### Population Structure (PCA)

- Used precomputed principal components  
- Evaluated variance explained (scree plot)  
- Visualized clustering by population  

- Selected top principal components (PC1–PC4) as covariates  

---

### Relatedness Assessment

- Used genetic relatedness matrix (GRM)  
- Examined kinship structure  

- Identified presence of:
  - Close relatives  
  - Extended relatedness  

- Incorporated GRM into association model  

---

### Null Model

- Fit linear mixed model using:
  - Outcome: height  
  - Covariates:
    - sex  
    - population  
    - PC1–PC4  
  - Random effect:
    - genetic relatedness (GRM)  

---

### Association Testing

- Performed genome-wide single-variant association tests  
- Used additive genetic model  

- Generated:
  - P-values  
  - Effect size estimates  
  - Minor allele counts  

---

### Result Evaluation

- Created Q-Q plot to assess inflation  
- Calculated genomic inflation factor (λGC)  
- Generated Manhattan plot  

- Identified:
  - Most significant variant  
  - Number of genome-wide significant loci  

---

## Technologies Used

- R  
- GENESIS  
- SNPRelate  
- GWASTools  
- tidyverse  
- qqman  
- ggplot2  

---

## Key Features

- End-to-end GWAS pipeline  
- Variant quality filtering  
- Population stratification correction  
- Mixed model association testing  
- Visualization of GWAS results  

---

## Key Skills Demonstrated

- Genome-wide association analysis  
- Linear mixed modeling  
- Population genetics (PCA, stratification)  
- Handling imputed genotype data  
- Statistical analysis of complex traits  
- Data visualization (Q-Q plots, Manhattan plots)  

---

## Notes

- Height is modeled as a continuous phenotype using a linear model  
- Principal components are included to control for ancestry  
- Genetic relatedness is accounted for to reduce confounding  
- Genomic inflation factor indicates well-controlled population structure  

---

## Author

Lakshita Arunkumar
