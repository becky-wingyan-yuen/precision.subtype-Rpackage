# On Data Normalization for Tumor Subtyping with microRNA data

## Contents

- [Repo Contents](#repo-contents)
- [Software dependencies](#software-dependencies)
- [Installation Guide](#installation-guide)
- [Demo](#demo)

# Repo Contents

- [R](./R): `R` code.
- [data](./data): the example data for the demo.
- [man](./man): help manual.

# Software dependencies

Before installing the `precision.subtype` package, users should have installed `R` with version 3.5.0 or higher.


### Package dependencies

Users should install the following packages prior to installing `precision.subtype`, from an `R` session:

```
if (!require("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
BiocManager::install("sva")
BiocManager::install("vsn")
```

# Installation Guide

From an `R` session, type:

```
require(devtools)
install_github("becky-wingyan-yuen/precision.subtype-Rpackage") 
```


# Demo

Please check the user's guide for the detailed instructions on how to use the functions in the package. You may also run the following code in the `R` session:

```
library(precision.subtype)

data("example_data", package = "precision.subtype")

uni_true_cluster = rep(NA,dim(example_data)[2])
uni_true_cluster[which(substr(colnames(example_data),7,7)=="E")] = 1
uni_true_cluster[which(substr(colnames(example_data),7,7)=="V")] = 2

results = cluster_other(dat = example_data, true_cluster = uni_true_cluster, 
						clust_method = "kmeans")
						
str(results)
```


