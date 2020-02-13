# R Package - Capybara
Capybara is a tool to measure cell identity and fate transitions. This approach is designed to measure cell identity as a continuum, at a single-cell resolution. Capybara enables classification of discrete entities as well as cells with multiple identities. This package have a dependency on R version (R >= 3.5.0). For details regarding the methods, usage and application, please refer to the following papaer - *\<Fill this in\>*.

## Installation
### Dependencies
Most dependency package can be installed along with Capybara through CRAN. The following dependency may need to be installed manually through BioConductor (Instructions can also be found here: https://bioconductor.org/).

Install BiocManager
```r
install.packages("BiocManager")
```
Install dependency packages
```r
BiocManager::install("limma")
```

### Install the package
Install devtools
```r
install.packages("devtools")
```
Install the package from GitHub.
```r
library("devtools")
devtools::install_github("morris-lab/Capybara")
```
Load the package
```r
library("Capybara")
```

## Step 1: Tissue-Level Classification
### Application of quadratic programming on reference and sample single-cell dataset using a bulk reference
Bulk transcriptome profiles of all tissues are mined from ARCHS4, a platform that contains most published RNA-seq and ChiP-seq datasets (Lachmann et al.,  2018). ARCHS4 obtains raw datasets from the Gene Expression Omnibus (GEO), realigned and processed through a uniform pipeline. We filtered to contain only poly-A and total RNA-seq data from C57BL/6 mice. With further filtering and preprocessing (details can be found in the method section of the paper), we landed with a reference of a total of 30 tissues. We provide our mined bulk references, including a matrix in raw counts and a matrix in reads per kilobase per million (RPKM), as a part of the Capybara package. Selection of your preferred normalization method can be applied to raw counts.

Load the bulk reference.
```r
# File path
bulk.raw.path <- system.file("extdata", "Bulk Reference Raw.Rds", package = "CellTagR")
bulk.rpkm.path <- system.file("extdata", "Bulk Reference RPKM.Rds", package = "CellTagR")
# Read the matrices
bulk.raw <- readRDS(bulk.raw.path)
bulk.rpkm <- readRDS(bulk.rpkm.path)
```

### Identification of tissue correlate in the reference to the sample single-cell dataset
## Step 2: Generation of a High-Resolution Custom Reference, and Continuous Identity Measurement
### Systematic construction of a high-resolution reference
### Application of quadratic programming on the self-established reference with the sample
## Step 3: Discrete Cell Type Classification and Multiple Identity Scoring
### Empirical p-value calculation
### Binarization with Mann-Whitney
### Classification
## Analysis of Cells with Multiple Identities
