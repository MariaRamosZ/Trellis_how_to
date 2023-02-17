**Trellis: Hierarchical Tree-Based Single-Cell Treatment Effect Analysis**

Trellis is a tool for hierarchical classification of single-cell samples that enables the fast and efficient calculaion of distances across thousands of distributions containing single-cell information. Further details on Trellis and its applicability in a single-cell drug screening of >2.500 heterocellular 3D samples is available in our [pre-print](https://www.biorxiv.org/content/10.1101/2022.10.19.512668v2). We have also described [detailed demonstration of the different functionalities of Trellis and TreEMD and a step by step example](https://www.kaggle.com/code/mariaramosz/trellis)

Trellis consists of the following steps:
1. Design a fixed layer of markers based on prior knowledge and define +/- thresholds to classify the cells.
2. Define a -leaf runner- function that performs k-means hierarchical clustering on the subtrees from 1. 
3. Alternatively, define a -tree runner- function that performs k-means hierarchical clustering on the dataset (skipping step 1). This is refered to as TreEMD.
4. Calculate parallel differential abundance between variables and internal conotrols (This is called -pairing- and it is also an optional step.
5. Use PHATE on the resulting abundance matrix from 2, 3 or 4.

Here is a representation of Trellis components, that can be used separately depending on the experimental question and the complexity of the dataset. 

![plot](https://github.com/MariaRamosZ/Trellis_how_to/blob/main/Ablation_draw.png)


By combining steps 1-4, we obtain different strategies to analyse large-scale datasets and create simple representations of the data. These are paire/unpaired TreEMD/Trellis:

![plot](https://github.com/MariaRamosZ/Trellis_how_to/blob/main/Trellis_squares_concusion.png)

All four methods described here - TreEMD, Paired TreEMD, Unpaired Trellis, and Trellis - are useful methods for different purposes. TreEMD enables a fast optimal transport calculation of tree-ground distances between thousands of conditions when no specific weighting is required. These can be paired (Paired TreEMD) to internal controls to solve issues such as variability between samples or batch effects. Unpaired Trellis enables specific weighting of markers while still calculating efficiently tree-distances across samples when there is not a specific control (e.g. if the aim is to compare the baseline phenotype of all PDOs, without including treatments or CAF co-cultures). Finally, Paired Trellis enables the calculation of paired tree-ground distances, weighting for specific markers or features. 
