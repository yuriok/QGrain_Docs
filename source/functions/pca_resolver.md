---
title: PCA Viewer
date: 2021-05-28 15:25:12
---

[Principal component analysis](https://en.wikipedia.org/wiki/Principal_component_analysis) (PCA) is a widely used tool to handle high-dimension data. As typically high-dimension data, grain-size distributions also could be processed by PCA. QGrain has integrated the basic PCA to extract the major variations of GSDs. The interface is very simple:

1. Just click the `Load Dataset` button to load your GSDs.
2. Select the number of PCs.
3. Click the `Perform` button to execute the PCA algorithm.
4. Check the explained variances of PCs (the percentages in the legend) to determine whether to add/reduce a component. If the sum of them is less than 90%, it means the number is not enough. If some minor components have very small variances, consider reducing the number.
5. If you are sure the number is appropriate, click the `Save` button to save the PCA result to an Excel file.

![The screenshot of PCA Resolver's interface](/images/pca.png)
