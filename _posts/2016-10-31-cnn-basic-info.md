---
layout: post
title: CNN各层介绍
categories: 
description: 简要介绍卷积神经网络中卷积层、池化层、归一化层、全连接层
及GEMM等等。
keywords: CNN
---

本文主要针对Convolutional Layer, Pooling Layer, Normalization Layer 和 Fully-Connected Layer进行了介绍，同时介绍了卷积运算中矩阵乘法的具体实现方法。

### Convolutional Layer(depth, stride and zero-padding)
![](/images/posts/cnn/convolutional-layer-basic-info.png)


### 参考
https://petewarden.com/2015/04/20/why-gemm-is-at-the-heart-of-deep-learning/
http://cs231n.github.io/convolutional-networks/#conv
