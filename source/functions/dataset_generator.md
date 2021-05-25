---
title: Dataset Generator
date: 2021-05-22 22:45:24
mathjax: true
---

This module is designed to generate the artificial datasets for the test of algorithms. If you want to try QGrain but has not any dataset, this module may be helpful. Or, if you are not clear with the functions and settings of the algorithms provided in QGrain, you can generate a series different datasets to explore their impacts. Of course, it could be used to generate some difficult datasets to test the performances of these algorithms. By generating a similar dataset as your real-world dataset, you could make sure whether these algorithms could handle your real-world dataset well, because all original information of an artificial dataset is known.

## Method of generation

A polymodal sample could be regarded as the mixture of several unimodal sub-populations, and the sub-population could be associated to a certain sedimentary process. Based on this theoretical model, it's very easy to generate artificial samples. We use the [Skew Normal](https://en.wikipedia.org/wiki/Skew_normal_distribution) distribution as the elementary distribution to generate the sub-populations. Skew Normal distribution is base the Normal (Gaussian) distribution, but provides an additional parameter to control the skewness. Therefore, it's more flexible than Normal distribution, each elementary distribution has three parameters, `shape` ($\alpha$), `location` ($\mu$) and `scale` ($\sigma$). The `shape` ($\alpha$) controls its skewness, when $\alpha=0$, it becomes the Normal distribution. **Note: due to its mathematical definition, the the skewness ($S_k$) is limited to the interval $(-1,1)$.** The interval integral should be applied to the probability density function (PDF) to transform it to frequency. Multiply the proportions of sub-populations to their frequencies, and then sum them, the mixed frequency is obtained. By calculating the frequency of each grain-size class, we can get the artificial sample. In order to simulate the actual observation, values will be rounded to the precision (e.g., 0.01%), and a group of Gaussian noise (an order of magnitude less than precision) will be overlaied on it. To make the samples random, each parameter is randomly generated and controled by mean $\mu_p$ and standard deviation $\sigma_p$ of a normal distribution.

## Mathematical definition

Let $\phi(x)$ denote the PDF of standard Normal distribution, there is

$$\phi(x)=\frac{1}{\sqrt{2\pi}}\exp\left(-\frac{x^2}{2}\right),$$

with the cumulative distribution function given by

$$\Phi(x) = \int_{-\infty}^{x} \phi(t)\ dt = \frac{1}{2}\left[1+\operatorname{erf}\left(\frac{x}{\sqrt{2}}\right)\right],$$

where $\operatorname{erf}$ is the [error](https://en.wikipedia.org/wiki/Error_function) function. Then the PDF of the Skew Normal distribution with parameter $\alpha$ is given by

$$f(x)=2\phi(x)\Phi(\alpha x).$$

To add location ($\mu$) and scale ($\sigma$) parameters, one makes the usual transform $x\rightarrow{\frac{x-\mu}{\sigma}}$. Then, the PDF becomes

$$f(x)={\frac{2}{\sigma}}\phi \left({\frac{x-\mu}{\sigma}}\right)\Phi \left(\alpha \left({\frac{x-\mu}{\sigma}}\right)\right).$$

To transform density to frequency, a interval integral should be applied

$$y_i = \int_{\phi_i-\frac{\delta}{2}}^{\phi_i+\frac{\delta}{2}} f(\phi_i),$$

where $y_i$ is the frequency of i-th grain-size class, $\phi_i$ is its grain-size in $\phi$, $\delta$ is the interval of two grain-size classes (in $\phi$).

Mixed frequency is

$$y_{mixed} = p_1 \cdot y_1 + p_2 \cdot y_2 + \cdots + p_c \cdot y_c,$$

where $p_c$ is the proportion of the c-th component.

## Interface

The figure below shows the interface of `Dataset Generator`. At the `Sampling` box, you can control the sampling settings, i.e., sampling range, interval ($N_{classes}$) and precision. In addition, you can change $N_{components}$ to control the number of component distributions to be mixed, it also controls the number of widgets in the `Random Parameter` box. By clicking the `Preview` button, artificial samples will be generated and displayed (in `Preview` box) successively, using the random parameters in the `Random Parameter` box. Each row of widgets is corresponding to the $\mu_p$ and $\sigma_p$ of a parameter. Finally, adjust the number of samples ($N_{samples}$) and click the `Generate` button, the artificial dataset will be saved into a Excel file. Click [here](/datasets/artificial_dataset_example.xlsx) to download an example file.

![The screenshot of Dataset Generator's interface](/images/dataset_generator.png)
