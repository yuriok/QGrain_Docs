---
title: SSU Resolver
date: 2021-05-30 15:42:01
mathjax: true
---

The interface of SSU is the most complex between these modules. But don't be worry, these parameters and panels are designed to make you have the ability to handle the most difficult samples, and it's no need to do tedious adjusting work for all samples.

![The screenshot of SSU Resolver's interface](/images/ssu.png)

Click the `Load Dataset` button to load the grain-size distributions. Click [here](/tutorials/load_gsds) to see the tutorial on loading the dataset. After loading, you can see the number of samples ($N_{samples}$) has been displayed. Also, the name of the first sample will be displayed. You can adjust the `Sample Index` to switch the current sample to be fitted.

You can select the SSU `Resolver`, one option is the neural SSU, another is the classic SSU. The neural SSU is similar to NNEMMA. Usually, the classic SSU has better performance, but the fitting process of neural SSU is normal, this makes that the neural SSU is more suitable for the analysis of the natures of the distance function. You can click the `Configure Fitting Algorithm` button to open the dialog to adjust the algorithm settings. The dialogs for the neural and classic SSU algorithms are different. Click the `Distribution Type` combo box to select an appropriate elementary distribution, and adjust the $N_{components}$ to an appropriate value.

Click the `Single Test` button to try fitting with default settings. You can see the fitting result in the chart below, and the result will be added to the right `Result` table. You can select the result in the table and right-click to pop up the menu. In this menu, you can display the variations of distance function, the distribution chart, and the animation of the fitting process.

![The animation of the fitting process of SSU](/videos/ssu.gif)

If it did not find the proper components (end-members), you can adjust the parameters and retry it. Increase the precision and enable the global optimization (GO) process will help it to find the components. If your sample has more than 3 components and the proportions of some components are very low, it's recommended to click the `Manual Test` to fitting the current sample manually. At the manual fitting panel, you can give some suggestions to each component. No need to be very accurate, for most conditions, you just need to move the mean values to the approximate locations. And click the `Try` button to fit the sample with your suggestions. If you are satisfied with this result, you can click the `Confirm` button to save this result and close this panel. If the result is not good, set the parameters more accurately and consider that whether the $N_{components}$ is enough.

![The screenshot of SSU Manual Fitting Panel's interface](/images/ssu_manual.png)

If it could find the proper components, you can click the `Test Next` button to fit the next sample. Or you can click the `Continuous Test` button to fit all samples in order.

If your dataset is very complex, for example, the $N_{components}$ is not constant. You should use the reference mechanism to reduce the workload. You can fit some typical samples manually, and select these correct results, and right-click to mark them as references. And then, you can click the `Continuous Test` button to fit all samples automatically. The algorithm will calculate the similarities between the current sample and references, and use the most similar result as a reference to fit the current sample. **Note: if there is only one marked result in the `Reference` table, all samples will use this result as the reference.**

If all samples have been fitted, you can right-click in the `Result` table to select the actions to detect the outliers. If there are some outliers, you can discard or retry them.

Finally, you can select the `Save Excel` action to save the results into an Excel file. **It's recommended to also save the results into a binary dump file because the dump file could record the fitting history and could be checked later.**
