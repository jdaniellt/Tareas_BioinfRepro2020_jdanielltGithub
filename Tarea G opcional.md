## Tarea opcional G

### Author: José Daniel Lara-Tufiño

### Summary of a pipeline for choosing the optimal clustering threshold in RADseq studies and the ipyrad software for generating the necessary input files to the pipeline

#### Pipeline abstract:

To propose robust homology hypotheses in RADseq or ddRADseq studies, it is necessary to consider a parameter that allows evaluating how divergent are two sequences that present alleles of the same homologous locus, and not to consider these true homologs as paralogs loci (McCartney-Melstad *et al* ., 2019), this parameter is known as **grouping threshold (CT)** in pyrad and ipyrad. If the grouping threshold is set too low (for example 0.84), the paralogue regions can be grouped within or between samples, and can be erroneously incorporated as orthologs, in contrast, if a grouping threshold is set too high (for example 0.99) The true alleles of the orthologous loci can be considered as paralogs.

The level of genetic differentiation of the samples is the product of a wide range of factors such as geographical distribution, effective size of the population, mutation rate etc… So a specific grouping threshold should not be expected to be adequate for any study. In this sense, considering a **CT** of 0.95 as suggested in ipyrad may not be ideal. Considering this problem in the choice of **CT**, McCartney-Melstad *et al*. (2019) propose a pipeline to evaluate 12 different grouping thresholds (0.88-0.96), and find the appropriate **CT** for our study. For this, seven metrics based on population genetics theory and landscape genetics are evaluated: (**1**) Fraction of inferred paralogues; (**2**) Genetic variation; (**3**) Cumulative variance explained by major principal components; (**4**) Relationship between missingness and genetic divergence; (**5**) Slope of isolation by distance; (**6**) Phylogenetic resolution; (**7**) Empirical sequence data and clustering.

To implement this pipeline the following files obtained for each pyrad or ipyrad run are required: **s5_consens_stats.txt** for the metrics **1** and **2**; the file **.vcf** for metrics **3**, **4**, **5**. With reference to the software, it is required to download the pipeline scripts hosted at: https://github.com/atcg/clustOpt/ and install **RAxML**, **vcftools**, **Rstudio** and the following packages: SNPRelate, pheatmap, geosphere, grImport2 and dendextend. Additionally, it is necessary to generate two files (can be .txt) the **VcfListFile** (here are the absolute paths of all the .vcf files you want to evaluate) and another **file with the geographic coordinates** of the samples you analyzed .

Finally, after implementing each metric, we looked for concordances between the optimal **CT** recovered in most of the metrics, identifying the value of **CT** in which the true alleles at the opposite ends of the main axes of genetic variation begin to separate incorrectly into groups. different, allowing you to select **CT** just below this value.

#### iPyrad abstract




#### References

McCartney‐Melstad, E., M. Gidiş, and H. Bradley-Shaffer. 2019. An empirical pipeline for choosing the optimal clustering threshold in RADseq studies. *Molecular Ecology Resource* 00:1–10.

Eaton D. A. R., and I. Overcast. 2020. ipyrad: Interactive assembly and analysis of RADseq datasets. *Bioinformatics* 




