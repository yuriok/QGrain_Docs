---
title: HC Resolver
date: 2021-05-28 16:15:11
mathjax: true
---

[Hierarchical clustering](https://en.wikipedia.org/wiki/Hierarchical_clustering) (HC) is one kind of clustering method. The hierarchical algorithms provided by the [hierarchy](https://docs.scipy.org/doc/scipy/reference/cluster.hierarchy.html) sub-module in [SciPy](https://www.scipy.org/) have been integrated into QGrain. You can use this function to filter the typical samples, trim the dataset and take a brief classification of sedimentary facies.

Follow the procedures:

1. Click the `Load Dataset` button to load your GSDs.
2. Click the `Perform` button to check the initial result. You could see a dendrogram at the major interface. It shows the relationships of different samples. At the top, all samples are in the same cluster. Go down, the cluster will be split into two new clusters, and so on. At the bottom, each sample is in its cluster. If the number of samples is too great, it’s difficult to should all labels of the bottom layer. Hence, it’s truncated and only shows `p` bottom leaves, you can change the `p` to show more or fewer bottom leaves. **Note that `p` only affects the figure, it has no influence on the clustering result. The Nclusters parameter controls the number of clusters.**
3. Click the `Show Typical` button to display the first sample of each cluster. This process can be treated as screening typical samples.
4. Clicking the `Show All` button will display all samples of the same clusters in several individual figures.
5. If you are satisfied with these parameters, click the `Save` button to save the clustering results into an Excel file.
6. If you want to classify sedimentary facies, you must make sure that the number of clusters could distinguish different sedimentary facies. After that, you could map the clusters to certain sedimentary facies according to the geological settings and other evidence. **Note: Different functions to calculate the similarities between samples may have different susceptibilities of the transition of sedimentary facies, there is no research on which distance metric is more suitable for the classification of sedimentary facies. Therefore, the current version of QGrain only uses the whole GSD to calculate distances, this may ignore some minor sub-populations.**

![The screenshot of HC Resolver's interface](/images/hc.png)
