# Trellis: Hierarchical Tree-Based Single-Cell Treatment Effect Analysis

Here we demonstrate Trellis, a tool for hierarchical classification of single-cell samples that enables the fast and efficient calculaion of distances across thousands of distributions containing single-cell information. This is an interactive notebook, that can be run and edited to understand step by step the functionalities of Trellis and its derivates. 

The data set that we will be using is a subset of a larger dataset developped in our pre-print: 'Trellis Single-Cell Screening Reveals Stromal Regulation of Patient-Derived Organoid Drug Responses'. This dataset was created with Colorectal Cancer (CRC) Patient-Derived Organoids (PDOs) that were treated with a range of chemotherapies and targeted therapies a varied ranges of concentrations. PDOs were treated alone, but also in 3D co-cultures with CRC Cancer-Associated Fibroblasts (CAFs) to understand the influence of this cell type in the responses to therapies of PDOs from different CRC patients. 

In the pre-print, we present the data corresponding to PDOs from 10 different patients. For this demonstration, we use a subset of the data, using only one patient (PDO 21) and we will compare different treatments and culture conditions on these cells using Trellis. 

Trellis consists of the following steps:
1. Design a fixed layer of markers based on prior knowledge and define +/- thresholds to classify the cells.
2. Define a -leaf runner- function that performs k-means hierarchical clustering on the subtrees from 1. 
3. Alternatively, define a -tree runner- function that performs k-means hierarchical clustering on the dataset (skipping step 1). This is refered to as TreEMD.
4. Calculate parallel differential abundance between variables and internal conotrols (This is called -pairing- and it is also an optional step.
5. Use PHATE on the resulting abundance matrix from 2, 3 or 4.
