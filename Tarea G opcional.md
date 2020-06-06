## Tarea opcional G

### Author: José Daniel Lara-Tufiño

### Summary of a pipeline for choosing the optimal clustering threshold in RADseq studies and the ipyrad software for generating the necessary input files to the pipeline

#### Pipeline abstract:

Para proponer hipótesis de homología robustas en estudios RADseq o ddRADseq es necesario considerar un parámetro que permita evaluar qué tan divergentes son dos secuencias que presenten alelos del mismo locus homólogo, y no considerar estos homólogos verdaderos como loci parálogos (McCartney-Melstad *et al*., 2019), este parámetro se conoce como **umbral de agrupmiento (CT)** en pyrad y ipyrad. Si el umbral de agrupamiento se establece muy bajo (for example 0.84), las regiones parálogas se pueden agrupar dentro o entre muestras, y se pueden ser incorporados erróneamente como ortólogos, en contraparte, si se establece un umbral de agrupación demasiado alto (for example 0.99) los alelos de verdaderos de lo loci ortólogos pueden considerarse como parálogos. 

El grado de diferenciación genética de las muestras es producto de una amplia gama de factores como la distribución geográfica, tamaño efectivo de la población, tasa de mutación etc… Así que no debe esperarse que un umbral de agrupamiento específico sea adecuado para cualquier estudio. En este sentido considerar un **CT** de 0.95 como se suguiere en ipyrad podría no ser lo ideal. Considerando esta problemática en la elección del **CT**, McCartney-Melstad *et al*. (2019) proponen una pipeline para evaluar 12 diferentes umbrales de agrupación (0.88-0.96), y encontrar el **CT** adecuado para nuestro estudio. Para ello se evaluan siete métricas basadas en la teoría de genética de poblaciones y en genética del paisaje: (**1**) Fraction of inferred paralogues; (¨**2**) Genetic variation; (**3**) Cumulative variance explained by major principal components; (**4**) Relationship between missingness and genetic divergence; (**5**) Slope of isolation by distance; (**6**) Phylogenetic resolution; (**7**) Empirical sequence data and clustering.

Para implementar esta pipeline se requieren los siguientes archivos obtenidos por cada corrida de pyrad o ipyrad: **s5_consens_stats.txt** para las métricas **1** y **2**; the file **.vcf** para las métricas **3**, **4**, **5**. Con referencia a los software se requiere descargar la pipeline scripts alojados en: https://github.com/atcg/clustOpt/ e instalar **RAxML**, **vcftools**, **Rstudio** y las siguientes paqueterias: SNPRelate, pheatmap, geosphere, grImport2 y dendextend. Adicionalmente se rquieren generar dos archivo (pueden ser .txt) the **VcfListFile** (aquí van las rutas absolutas de todos los archivos .vcf que deseas evaluar) y otro **archivo con las coordenadas geográficas** de las mestras que analizaste.


