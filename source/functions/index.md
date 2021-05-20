---
title: Functions of QGrain
date: 2021-05-20 22:45:24
---

Table 1. The functions of current version of QGrain

|Function|Description|Module|
|-|-|-|
|Frequencey curve chart|Plot the chart of frequency curves of samples|[Dataset Viewer](./dataset_viewer)|
|Statistic parameters|Calculate the statistic parameters (e.g. mean, sorting, skewness, kurtosis) of grain-size distributions (GSDs)|[Dataset Viewer](./dataset_viewer)|
|GSD classification|Plot the gravel-sand-mud and sand-silt-clay diagrams of GSDs, also support the automatic classification of GSDs, including Folk’s (1954) and Blott & Pye’s (2012) classification scheme.|[Dataset Viewer](./dataset_viewer)|
|PCA|Apply the principal component analysis (PCA) algorithm to extract the major and minor signal series in a grain-size dataset.|
|Hierarchical clustering|Perform a hierarchical clustering algorithm to have an overall cognition and pick out the typical samples of a grain-size dataset. Also could be used to briefly classify the sedimentary facies.|
|EMMA|Provide a new end-member modelling analysis (EMMA) algorithm based on the basic neural network to unmix the grain-size distributions and extract the latent information of paleoenvironments and paleoclimates.|
|SSU|Single sample unmixing (SSU) is another unmixing method to separate the mixed grain-size distributions. Due to the natural difficulty of SSU problem, SSU may yield abnormal results and hence be underestimated. To satisfy the existing requirements, a new and enhanced SSU algorithm is provided.|
