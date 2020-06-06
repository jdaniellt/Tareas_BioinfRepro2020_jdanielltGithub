## Tarea opcional G

### Author: José Daniel Lara-Tufiño

### Summary of a pipeline for choosing the optimal clustering threshold in RADseq studies and the ipyrad software for generating the necessary input files to the pipeline

#### Pipeline abstract:

Para proponer hipótesis de homología robustas en estudios RADseq o ddRADseq es necesario considerar un parámetro que permita evaluar qué tan divergentes son dos secuencias que presenten alelos del mismo locus homólogo, y no considerar estos homólogos verdaderos como loci parálogos (McCartney-Melstad *et al*., 2019), este parámetro se conoce como **umbral de agrupmiento (CT)** en pyrad y ipyrad. Si el umbral de agrupamiento se establece muy bajo (for example 0.84), las regiones parálogas se pueden agrupar dentro o entre muestras, y se pueden ser incorporados erróneamente como ortólogos, en contraparte, si se establece un umbral de agrupación demasiado alto (for example 0.99) los alelos de verdaderos de lo loci ortólogos pueden considerarse como parálogos. 

El grado de diferenciación genética de las muestras es producto de una amplia gama de factores como la distribución geográfica, tamaño efectivo de la población, tasa de mutación etc… Así que no debe esperarse que un umbral de agrupamiento específico sea adecuado para cualquier estudio. En este sentido considerar un umbrl de grupamiento de 0.95 como se suguiere en ipyrad podría no ser lo ideal. Considerando esta problemática en la elección del CT, McCartney-Melstad *et al*. (2019)m proponen una pipeline para evaluar 12 diferentes umbrales de agrupación (0.88-0.96), y encontrar el CT adecuado para nuestro estudio. Para ello se evaluan siete métricas: (**1**) Fraction of inferred paralogous clusters; (¨**2**) The slope of genetic divergence versus geographic distance; **3**) The correlation of pairwise divergence with pairwise missingness; (**4**) Mean bootstrap values in a maximum likelihood tree building framework; (**5**) Total number of SNPs recovered; (**6**) Fraction of variance explained by the main principal components of genetic variation; (**7**) Heterozygosity.


