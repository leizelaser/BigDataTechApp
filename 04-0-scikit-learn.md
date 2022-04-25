# Scikit-learn 库
这个库集合了很多常用的机器学习算法，从简单的线性回归到K-neighbors, K-means等：
* Classification 分类
* Regression 回归
* Clustering 非监督聚类
* Dimensionality reduction 数据降维
* Model Selection 模型选择
* Preprocessing 数据预处理

此库自带数据集，可以进行简单的演示和测试。安装只需在anaconda中勾选即可。

我们参考Jake Vanderplas的[sklearn tutorial](github.com/jakevdp/sklearn_tutorial)，讲解机器学习的基本算法和操作。

## Regression 回归
线性回归/最小二乘法

## 支持向量机  Supported Vector Machine & Classification
* 线性可分的两点集间，寻找和两点集间距最大的直线。（其对偶问题可以引导出一cost function）
* 如果线性不可分，寻求最优的分割直线（最小化cost function）
* 如果是非线性可分，也可考虑升维-参数变换来区分

## 随机（决策）树/森林 Random (Decision) Trees/Forests & Classification
* 利用多棵树对样本进行训练并预测的一种 分类器

构造随机森林：
1. 一个样本容量为N的样本，有放回的抽取N次，每次抽取1个，最终形成了N个样本。这选择好了的N个样本用来训练一个决策树，作为决策树根节点处的样本。
2. 当每个样本有M个属性时，在决策树的每个节点需要分裂时，随机从这M个属性中选取出m个属性，满足条件m << M。然后从这m个属性中采用某种策略（比如说信息增益）来选择1个属性作为该节点的分裂属性。
3. 决策树形成过程中每个节点都要按照步骤2来分裂（很容易理解，如果下一次该节点选出来的那一个属性是刚刚其父节点分裂时用过的属性，则该节点已经达到了叶子节点，无须继续分裂了）。一直到不能够再分裂为止。注意整个决策树形成过程中没有进行剪枝。
4. 按照步骤1~3建立大量的决策树。

## 聚类 Clustering K-Means

## Density-GMM