---
title: EMMA Resolver
date: 2021-05-29 12:11:21
mathjax: true
---

This module has implemented a new EMMA algorithm (NNEMMA) which is based on the basic neural network. It not only supports nonparametric EMMA but also supports elementary distribution (e.g., Normal, Weibull, and Skew Normal distributions) constrained EMMA. In addition, you even can customize the end-members, if you could determine them by other methods, e.g., taking samples from the sources.

Follow the procedures:

1. Click the `Load Dataset` button to load your GSDs.
2. Click the `Configure Algorithm` button to open the dialog to adjust the parameters of the NNEMMA algorithm. If you are not sure how to adjust them, just keep the default settings and try the next procedure.
3. Click the `Distribution Type` combo box to select an appropriate elementary distribution. If you do not know which distribution type is more suitable, just try `Nonparametric` first.
4. Change the `Minimum N_members` and `Maximum N_members` parameters to your guess. It will try the number of end-members from the minimum to the maximum. If you just want to perform once, set them to the same value. If you are not sure that how many end-members your dataset has, you can perform a series of tests from 1 to 10. By observing the summary chart, you may find which number is more suitable. **Note: This statistic method is not fully correct for all datasets, more geological settings and other knowledge should be taking into the determination of the number of end-members. The number is very important because it will highly affect the results and the end-members must have their corresponding sedimentary mechanisms.**
5. The fitting process will be displayed by the progress bar, and if all tasks have finished, the results will be added to the right list. Select one and click the `Show` button to display the fitting result. In addition, you can click the `Remove` button to remove this result; click the `Save` button to save the result to an Excel file, or save all results in the list to a binary dump file for later view.
6. By observing the chart of the selected fitting result, you can judge that whether the algorithm has converged to the limit and whether the fitting result has unmixed the end-members well. You also can click the `Animated` checkbox to show the animation of the fitting process. By clicking the `Save` button in the chart (with `Animated` checked), you can save the fitting process into an `mp4` or `gif` file for later presentation. If the number of iterations is greater than 200, it's recommended to save it as an `mp4` file, because saving `gif` will take too much time and computer memory to compress, and even take up more space. If it did not converge to the limit, please increase the minimum and maximum $N_{iterations}$ in the algorithm settings. If the changes in distances are too volatile, you need to decrease the learning rate.
7. Adjust the settings until you are satisfied, save the corresponding result to an Excel file. It's recommended to save the binary dump file because all information could be saved. You can load the results from the dump file, and re-inspect them, plot the figure, and save the animation.

![The screenshot of EMMA Resolver's interface](/images/emma.png)

<video controls preload loop>
  <source src="/videos/emma.mp4" type="video/mp4">
  The saved animation of the fitting process of NNEMMA.
</video>
