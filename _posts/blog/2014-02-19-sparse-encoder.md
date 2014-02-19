---
layout: post
title: Sparse Auto-encoder
description: UFLDL学习笔记(一) 事物存在的合理性往往是让人意想不到的，如果我们善于思考和发现的话；自编码神经网络给我最大的惊喜是：别小瞧自编码器。不止如此，你会发现隐层也是很有意思的。
category: blog
---

本系列文章是学习[UFLDL][2]的学习笔记和心得。这次我们从神经网络讲开去，说说自编码器的东西。


##关于监督学习

监督学习是最容易入门的机器学习思想，作为人工智能领域最有力的工具，它操作简单却十分直观——给机器一组training data with label，通过算法处理，它便会为我们的testing data without label给出对应的label，恰好这个label就是我们想要的东西。因此这种思想在数字识别、语音识别、自动驾驶汽车以及提高人们对人类基因的认识上有成功的应用。

然而有监督学习(supervised learning)仍然有局限性。在使用回归模型时，我们根据现有数据的分布特征，选择线性或是更高次的多项式模型，亦或是logistic模型;使用SVM做分类问题时，数据集如何做变换，使得类之间尽可能出现明显的"簇"便是决定分类效果高低的关键。
这就是有监督学习的局限所在，它依赖于我们选择的特征。特征选择得好，模型效果/表现力就强。如此一来，我们将算法应用到新领域的时候，就希望有一个"专家"来告诉我们，什么样的变量有效。否则我们就要不断地对变量做变换，以提高模型性能。

在上杨坦老师开的'数据挖掘'课时有一个医疗领域的案例，恰能说明"行业经验"在数据挖掘实践中的作用。当时的数据是病人的血样指标，包括Na，K离子的含量等信息，以及对应的发病率。在对数据进行可视化时发现，单纯使用Na或K为特征，数据分布特征不明显，但当我们构造`Na/K`这个特征时，便发现了其与发病率的强相关性。
事实上，这个指标恰恰是医学上的重要指标。

正因如此，在Computer Vision、Audio Processing以及Natural Language Processing领域。目前有大量的研究人员在用他们的专业知识去寻找这些特征(features)，这无疑是非常耗费时间精力的事情，一旦新的问题出现，又需要重新构造特征。

Prof. Andrew Ng在CS294A的Lecture中这样说：
**_Once a good feature representation is given, a supervised learning algorithm can do well. But in such domains as computer vision, audio processing, and natural language processing, there’re now hundreds or perhaps thousands of researchers who’ve spent years of their lives slowly and laboriously hand-engineering vision, audio or text features. While much of this feature-engineering work is extremely clever, one has to wonder if we can do better. Certainly this labor-intensive hand-engineering approach does not scale well to new problems; further, ideally we’d like to have algorithms that can automatically learn even better feature representa- tions than the hand-engineered ones._**

问题是，我们能否想办法给出能自动生成有效特征的算法呢?这就是 **Sparse Autoencoder** 算法的目标，它是一种在unlabeled data中自动学习/寻找特征的算法。


##思路
[Sparse Autoencoder][3]的组织思路是这样的：介绍有监督学习中的神经网络及反向传播算法；随后展示如何以此建立无监督的自编码神经网络，最后引入稀疏性概念并建立

##Sparse Auto-encoder

$$
\begin{align*}
  & \phi(x,y) = \phi \left(\sum_{i=1}^n x_ie_i, \sum_{j=1}^n y_je_j \right)
  = \sum_{i=1}^n \sum_{j=1}^n x_i y_j \phi(e_i, e_j) = \\
  & (x_1, \ldots, x_n) \left( \begin{array}{ccc}
      \phi(e_1, e_1) & \cdots & \phi(e_1, e_n) \\
      \vdots & \ddots & \vdots \\
      \phi(e_n, e_1) & \cdots & \phi(e_n, e_n)
    \end{array} \right)
  \left( \begin{array}{c}
      y_1 \\
      \vdots \\
      y_n
    \end{array} \right)
\end{align*}
$$

$$
\exp{-\frac{x^2}{2}}
$$

$$
\frac{a}{b}
$$




[zihaolucky]:    http://zihaolucky.github.io  "zihaolucky"
[1]:    {{ page.url}}  ({{ page.title }})
[2]:  http://ufldl.stanford.edu/wiki/index.php/UFLDL教程