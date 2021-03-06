---
title: Functions of QGrain
date: 2021-05-22 22:45:24
---

You can check the table below for the functions provided by current version of QGrain. More functions are considering to be added, e.g. the CM diagram (Passega, 1964). If you has more requirements, please feel free to tell the [author](mailto:liuyuming@ieecas.cn).

|Function|Description|Link|
|-|-|-|
|Dataset Generator|Generate the artificial dataset to test the functions of QGrain, generating parameters could be fully customized.|[Dataset Generator](./dataset_generator)|
|Frequencey curve chart|Plot the chart of frequency curves of samples.|[Dataset Viewer](./dataset_viewer)|
|Accumulative curve chart|Plot the chart of accumulative curves of samples.|[Dataset Viewer](./dataset_viewer)|
|Frequencey 3D chart|Plot the GSDs of samples as a 3D surface, easy to recognize the variations of GSDs in the stratigraphic sequence.|[Dataset Viewer](./dataset_viewer)|
|Statistic parameters|Calculate the statistic parameters (e.g. mean, sorting, skewness, kurtosis) of grain-size distributions (GSDs).|[Dataset Viewer](./dataset_viewer)|
|Folk (1954)’s classification diagram|Plot the gravel-sand-mud and sand-silt-clay diagrams of Folk (1954)'s scheme.|[Dataset Viewer](./dataset_viewer)|
|Blott & Pye (2012)’s classification diagram|Plot the gravel-sand-mud and sand-silt-clay diagrams of Blott & Pye (2012)’s scheme.|[Dataset Viewer](./dataset_viewer)|
|GSD classification|Automatic classification of GSDs, including Folk (1954)’s and Blott & Pye (2012)’s classification scheme.|[Dataset Viewer](./dataset_viewer)|
|Principal component analysis|Apply the principal component analysis (PCA) algorithm to extract the major and minor signal series in a grain-size dataset.|[PCA Resolver](./pca_resolver)|
|Hierarchical clustering|Perform a hierarchical clustering (HC) algorithm to have an overall cognition and pick out the typical samples of a grain-size dataset. Also could be used to briefly classify the sedimentary facies.|[HC Resolver](./hc_resolver)|
|End-member modelling analysis|Provide a new end-member modelling analysis (EMMA) algorithm based on the basic neural network to unmix the grain-size distributions and extract the latent information of paleoenvironments and paleoclimates.|[EMMA Resolver](./emma_resolver)|
|Single sample unmixing|Single sample unmixing (SSU) is another unmixing method to separate the mixed grain-size distributions. Due to the natural difficulty of SSU problem, SSU may yield abnormal results and hence be underestimated. To satisfy the existing requirements, a new and enhanced SSU algorithm is provided.|[SSU Resolver](./ssu_resolver)|
