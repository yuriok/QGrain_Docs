---
title: A brief introduce of the QGrain software
date: 2021-05-20 16:37:45
---

## The aim of QGrain

![The logo of QGrain, Copyright 2021 Yuming Liu, All rights reserved](/images/icon.png)

QGrain aims to provide an easy-to-use and comprehensive analysis platform for grain-size distributions. QGrain has implemented many functions, however, there still are many useful tools that have not been contained. Hence, we published QGrain as an open-source project, and welcome other researchers to contribute their ideas and codes. Codes are available at this GitHub [repository](https://github.com/yuriok/QGrain/).

## Technical route

To achieve QGrain’s aim, the software techniques were advisedly chosen. [Python](https://www.python.org/), the programing language which has been widely used in scientific computation, machine learning, and many other fields, was chosen as the major developing language of QGrain. Python’s syntax is concise and easy to learn. And comparing to other same type languages, [R](https://www.r-project.org/) and [MATLAB](https://www.mathworks.com/), Python is open-source and FREE (can be modified at will, and need not pay), and its community is more prosperous. A large number of mature modules (e.g., [Matplotlib](https://matplotlib.org/), [NumPy](https://numpy.org/), [SciPy](https://www.scipy.org/), [scikit-learn](https://scikit-learn.org/), and [PyTorch](https://pytorch.org/)) could be used, which means many repetitive underlying codes need not be written, this enables developers could focus on their specific scientific problems. To make QGrain easy-to-use, it’s necessary to provide a well-designed [GUI](https://en.wikipedia.org/wiki/Graphical_user_interface/) for users who do not know to program. Till the latest version (0.3.2), near 9000 lines of codes were wrote and about 2/3 of them were used to build the GUI. The GUI of QGrain was based on the well-known [cross-platform](https://en.wikipedia.org/wiki/Cross-platform_software/) GUI platform, [Qt](https://www.qt.io/qt-for-python/), this makes QGrain is also cross-platform. QGrain also provides many charts with publishing quality base on the widely-used visualization library, [Matplotlib](https://matplotlib.org/).

## Quick install

We have packed the setup file for **Windows** users, just download and run it.

You can download the latest version from [GitHub](https://github.com/yuriok/QGrain/releases/).

Or, you can download it from [Google Drive](https://drive.google.com/drive/folders/1Z-xUVpxml9XHPWd0LOgxjtchCPMd1-tn?usp=sharing). For the users in China, you can download it from [Baidu Drive](https://pan.baidu.com/s/1hau7AruPkpgvzjF-mMCQaQ/), with code: 8bzg.

For Linux and Mac OS X users, you can install QGrain as a Python module.

```bash
pip3 install QGrain
```

Then, run it by the the command below.

```bash
python3 -m QGrain
```

Finally, you will see the `Console` interface of QGrain.

![The screenshot of initial interface](/images/console.png)

## Functions

The detialed introduce of these functions is [here](/functions).

* [Dataset Generator](/functions/dataset_generator)

* [Dataset Viewer](/functions/dataset_viewer)

## Tutorials

Click [here](/tutorials) to see more tutorials.

* [Advanced installation](/tutorials/install)

## Contact

It is recommended to use GitHub's [Issues](https://github.com/yuriok/QGrain/issues/) to discuss and report problems. Or, you can contact the author below, directly.

Yuming Liu, a PhD student of IEECAS, [liuyuming@ieecas.cn](mailto:liuyuming@ieecas.cn)
