Convolutional Recurrent Neural Network
======================================

This software implements the Convolutional Recurrent Neural Network (CRNN) in pytorch.
Origin software could be found in [crnn](https://github.com/bgshih/crnn)

Run demo
--------
A demo program can be found in ``demo.py``. Before running the demo, download a pretrained model
from [Baidu Netdisk](https://pan.baidu.com/s/1pLbeCND) or [Dropbox](https://www.dropbox.com/s/dboqjk20qjkpta3/crnn.pth?dl=0). 
This pretrained model is converted from auther offered one by ``tool``.
Put the downloaded model file ``crnn.pth`` into directory ``data/``. Then launch the demo by:

    python demo.py

The demo reads an example image and recognizes its text content.

Example image:
![Example Image](./data/demo.png)

Expected output:
    loading pretrained model from ./data/crnn.pth
    a-----v--a-i-l-a-bb-l-ee-- => available

Dependence
----------
* [warp_ctc_pytorch](https://github.com/SeanNaren/warp-ctc/tree/pytorch_bindings/pytorch_binding)
* lmdb

Train a new model
-----------------
1. Construct dataset following [origin guide](https://github.com/bgshih/crnn#train-a-new-model). If you want to train with variable length images (keep the origin ratio for example), please modify the `tool/create_dataset.py` and sort the image according to the text length.
2. Execute ``python train.py --adadelta --trainRoot {train_path} --valRoot {val_path} --cuda``. Explore ``train.py`` for details.

Exercise 1 (10 points): Statistical Measures [Pen and Paper]
============================================================

Whenever we deal with a dataset to solve a particular problem, it is helpful to first analyse the
data and extract some information. In this exercise, we are going to take a look at statistical
measures which are very basic tools and describe the data by a single number only. However,
this does not mean that they are useless or less important than other (more complex) analysis.
Every measure conveys a special meaning and must be applied with care since they are also
easily misinterpreted.
Here, we are using a small one-dimensional dataset
	
	𝑋 = {5, 4, 10, 1, 5, 25} (1)

where we can easily calculate the results by hand. Besides the measures, we are going to work
with a box-and-whisker plot which is a very important visualization technique summarizing a
lot of information.

Table 1: Overview of statistical measures. Please refer to the script for the definition of the
measures.

Measure | Required scaling | Value of measure for 𝑋
---- | ------ | -------Mode
Mode |Nominal| 5
Arithmetic mean ​𝑥 |Interval|(1+4+5+5+10+25)/6 = 8.333
Quantile ​𝑥​̃0.25 |Ordinal| 4
Median ​𝑥​̃0.5 |Ordinal |5
Range ​𝑅 |Interval |25-1 = 24
Interquartile range ​𝑄 |Interval |10-4 = 6
Variance ​𝑠​2 |Interval| 𝑠​2 = 75.066
(Note: therefore s = 8.664)
Skewness ​𝑔 |Interval |0.6667 (+ve)
Quartile skewness ​𝑔𝑄 |Ratio| 1