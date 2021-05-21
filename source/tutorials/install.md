---
title: Advanced installation
date: 2021-05-21 19:08:45
---

**Note: this way of installation is for the user who has experience in Python and Shell (i.e. command-line interface) or is willing to take the time to learn them.**

The **QGrain** software actually is a [Python](https://www.python.org/) module. So, if you have experience with Python, you can install it from [PyPI](https://pypi.org/project/QGrain/). This way of installation is more flexible, because the source codes can be modified easily. If there is a low level bug, you can modify the codes to timely fix it by yourself, no need to wait for the author of QGrain to fix it and publish the new version. In addition, you can write codes to use QGrain for some special application scenarios. For example, load the fitting results and customize the plots. Python and the third-party modules used in QGrain are all **cross-platform**, this means QGrain also is cross-platform, theoretically. However, some dependent modules (e.g., `PyTorch`) may not has a binary distribution for some unpopular operating systems, you may need to solve this dependency problem by compiling these modules from sources. Don't warry, it's not a problem for most operating systems.

## Install the Python

For `Linux` and `Mac OS X` users, a relatively old version of Python is built-in. `Windows` users need to install it from the offical [website](https://www.python.org/).

You can run the command `python` or `python3` in your `Terminal` to check if Python is existing.

**Note: Using `python` or `python3` depends on the alias or the filename of your Python3 interpreter, rather than you can choose Python2 or Python3 at liberty. Python2 is too old and has been obsoleted. For `Unix` like operating systems, `python3` usually is correct, and for `Windows`, `python` usually is correct.**

If you have Python3 installed on your computer, you can see the text like below. You can see the version of your Python. And the `>>>` symbols hint you that you have entered the interactive model of Python's interpreter. Type `quit()` to quit this model and back to the terminal.

```bash
username:~$ python3
Python 3.8.5 (default, Jan 27 2021, 15:41:15)
[GCC 9.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

If there is no Python, just follow the guide in the offical [website](https://www.python.org/) of Python to install it.

## Install QGrain

We have uploaded QGrain to [PyPI](https://pypi.org/project/QGrain/). You can install it by running `pip` or `pip3` in the `Terminal`.

```bash
pip3 install QGrain
```

For the users in China, using the mirror provided by Tsinghua University may be faster.

```bash
pip3 install -i https://pypi.tuna.tsinghua.edu.cn/simple QGrain
```

Run `pip3 install -U QGrain` to check and update QGrain.

If you do not have the `pip`, just use the package management tool to install it.

For example, the command for `Ubuntu` is:

```bash
sudo apt update
sudo apt install python3-pip
```

In addition, you can download the codes from our Github [repository](https://github.com/yuriok/QGrain/).

You can clone the repository by running the following command if you have `git` installed.

```bash
git clone https://github.com/yuriok/QGrain.git
```

Then, you will see the similar information below.

```bash
username:~$ git clone https://github.com/yuriok/QGrain.git
Cloning into 'QGrain'...
remote: Enumerating objects: 2792, done.
remote: Counting objects: 100% (1526/1526), done.
remote: Compressing objects: 100% (742/742), done.
remote: Total 2792 (delta 1042), reused 1244 (delta 781), pack-reused 1266
Receiving objects: 100% (2792/2792), 2.02 MiB | 24.00 KiB/s, done.
Resolving deltas: 100% (1871/1871), done.
```

When it finished, the source codes have been downloaded into the `QGrain` folder of the working directory. Change the working directory to `QGrain`, and use `pip` to install it.

```bash
cd QGrain
pip3 install .
```

Or, you can download the pure codes directly by clicking [here](https://github.com/yuriok/QGrain/archive/master.zip). If you choose to download the zip file, please extract it. Then, you should change the directory to the extracted folder, and run the command `pip3 install .`.

## Try QGrain

Now, everything is ok. You can run `python3 -m QGrain` command in your terminal to start the GUI of QGrain.

If it goes well, you can see the interface below.

![The screenshot of initial interface](/images/console.png)

Also, you can use QGrain as a Python module, import it in your Python codes and use the `class` and `function` provided by QGrain. For example, you can calculate the statistic parameters using the following codes. **Note: the APIs of QGrain will be changed a lot, it's not recommended to use this method for common requirements.**

```python
# import the method to generate artificial samples
from QGrain.models.artificial import get_random_sample
# import the method to calculate the statistic parameters
from QGrain.algorithms.moments import get_moments

# generate test sample
sample = get_random_sample()
# check the generating parameters
print(sample.parameter.fractions)
for comp in sample.parameter.components:
    print(comp.moments)

# calculate the statistic parameters
moments = get_moments(sample.classes_μm, sample.classes_φ, sample.distribution, FW57=False)
print(moments)

```

You will see the calculated statistic parameters and the classification groups like below:

```python
({'mean': 12.565072409303028, 'std': 4.706158375497856, 'skewness': -0.7787966067475761, 'kurtosis': 2.7317145943361987, 'std_description': 'Very poorly sorted', 'skewness_description': 'Fine skewed', 'kurtosis_description': 'Mesokurtic', 'mean_description': 'Medium Silt', 'mode': 35.565588200778436, 'modes': (5.023772863019158, 35.565588200778436), 'median': 19.416585200230955, 'GSM_proportion': (0.0, 0.1187, 0.8813), 'SSC_proportion': (0.1187, 0.7322, 0.1491), 'BGSSC_proportion': (0.0, 0.0, 0.1187, 0.7322, 0.1491), 'textural_group_Folk54': 'Sandy Slit', 'textural_group_BP12_symbol': '(s)(c)SI', 'textural_group_BP12': 'Slightly Sandy Slightly Clayey Silt'}, {'mean': 6.314437204649162, 'std': 2.234549872134817, 'skewness': 0.7787966067475749, 'kurtosis': 2.731714594336198, 'std_description': 'Very poorly sorted', 'skewness_description': 'Fine skewed', 'kurtosis_description': 'Mesokurtic', 'mean_description': 'Medium Silt', 'mode': 4.813374166052885, 'modes': (7.637013046707143, 4.813374166052885), 'median': 5.686566693851849, 'GSM_proportion': (0.0, 0.1187, 0.8813), 'SSC_proportion': (0.1187, 0.7322, 0.1491), 'BGSSC_proportion': (0.0, 0.0, 0.1187, 0.7322, 0.1491), 'textural_group_Folk54': 'Sandy Slit', 'textural_group_BP12_symbol': '(s)(c)SI', 'textural_group_BP12': 'Slightly Sandy Slightly Clayey Silt'})
```

## Enable CUDA

Some functions (e.g., EMMA) of QGrain could use CUDA to accelerate the computation. By default, QGrain will install the CPU version of PyTorch, because not all users have a high-performance NVIDA GPU, and CPU is faster to handle a small dataset. It needs more steps to enable the CUDA, not only install a CUDA version of PyTorch, [CUDA Toolkit](https://developer.nvidia.com/cuda-toolkit/) and [CUDNN](http://developer.nvidia.com/cudnn/) also should be installed. Follow the guides of [PyTorch](https://pytorch.org/) and NVIDA to install them. If all of them have been installed, the `CUDA` option in the `device` setting could be selected.
