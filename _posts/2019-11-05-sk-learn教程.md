## sk-learn教程

### 一、监督学习

#### 1. 广义线性模型

定义一个定常的线性系统如下：

![](https://sklearn.apachecn.org/docs/0.21.3/img/4ee9f6c666393981b6458e54c3ec89d0.jpg)

##### 1.1 普通最小二乘法

[`LinearRegression`](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html#sklearn.linear_model.LinearRegression) 拟合一个带有系数 ![w = (w_1, ..., w_p)](https://sklearn.apachecn.org/docs/0.21.3/img/3f5adc0c9b0e51a0759ed6ac49f94431.jpg) 的线性模型，使得数据集实际观测数据和预测数据（估计值）之间的残差平方和最小。其数学表达式为:

![\underset{w}{min\,} {|| X w - y||_2}^2](https://sklearn.apachecn.org/docs/0.21.3/img/1b6228a71a038f66ac7b8a2743adf4e7.jpg)

> ```python
> >>> from sklearn import linear_model
> >>> reg = linear_model.LinearRegression()
> >>> reg.fit ([[0, 0], [1, 1], [2, 2]], [0, 1, 2])
> LinearRegression(copy_X=True, fit_intercept=True, n_jobs=1, normalize=False)
> >>> reg.coef_
> array([ 0.5,  0.5])
> ```

普通最小二乘法的一些缺点：其依赖于模型各项的相互独立性。当各项是相关的，且设计矩阵 ![X](https://sklearn.apachecn.org/docs/0.21.3/img/43c1fea57579e54f80c0535bc582626f.jpg) 的各列近似线性相关，那么，设计矩阵会趋向于奇异矩阵，这种特性导致最小二乘估计对于随机误差非常敏感，可能产生很大的方差。例如，在没有实验设计的情况下收集到的数据，这种多重共线性（multicollinearity）的情况可能真的会出现。

##### 1.2 岭回归

[`Ridge`](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Ridge.html#sklearn.linear_model.Ridge) 回归通过对系数的大小施加惩罚来解决 [普通最小二乘法](https://sklearn.apachecn.org/docs/0.21.3/2.html#1111-普通最小二乘法复杂度) 的一些问题。 岭系数最小化的是带罚项的残差平方和，

![\underset{w}{min\,} {{|| X w - y||_2}^2 + \alpha {||w||_2}^2}](https://sklearn.apachecn.org/docs/0.21.3/img/c7e49892dca2f0df35d1261a276693f2.jpg)

其中， ![\alpha \geq 0](https://sklearn.apachecn.org/docs/0.21.3/img/a4775baaa990a4fbffcfc2688e3b5578.jpg) 是控制系数收缩量的复杂性参数： ![\alpha](https://sklearn.apachecn.org/docs/0.21.3/img/d8b3d5242d513369a44f8bf0c6112744.jpg) 的值越大，收缩量越大，模型对共线性的鲁棒性也更强。

> ```python
> >>> from sklearn import linear_model
> >>> reg = linear_model.Ridge (alpha = .5)
> >>> reg.fit ([[0, 0], [0, 0], [1, 1]], [0, .1, 1])
> Ridge(alpha=0.5, copy_X=True, fit_intercept=True, max_iter=None,
>  normalize=False, random_state=None, solver='auto', tol=0.001)
> >>> reg.coef_
> array([ 0.34545455,  0.34545455])
> >>> reg.intercept_
> 0.13636...
> ```

##### 1.3 Lasso

##### 1.4 多任务Lasso

##### 1.5 弹性网络

`弹性网络` 是一种使用 L1， L2 范数作为先验正则项训练的线性回归模型。 这种组合允许拟合到一个只有少量参数是非零稀疏的模型，就像 [`Lasso`](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Lasso.html#sklearn.linear_model.Lasso) 一样，但是它仍然保持了一些类似于 [`Ridge`](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Ridge.html#sklearn.linear_model.Ridge) 的正则性质。我们可利用 `l1_ratio` 参数控制 L1 和 L2 的凸组合。

弹性网络在很多特征互相联系的情况下是非常有用的。Lasso 很可能只随机考虑这些特征中的一个，而弹性网络更倾向于选择两个。

在实践中，Lasso 和 Ridge 之间权衡的一个优势是它允许在循环过程（Under rotate）中继承 Ridge 的稳定性。

在这里，最小化的目标函数是

![\underset{w}{min\,} { \frac{1}{2n_{samples}} ||X w - y||_2 ^ 2 + \alpha \rho ||w||_1 +\frac{\alpha(1-\rho)}{2} ||w||_2 ^ 2}](https://sklearn.apachecn.org/docs/0.21.3/img/9b9ee41d276ad49322856b95cb6c7e43.jpg)

##### 1.10 贝叶斯回归

##### 1.11 logistic 回归

虽然名字里有 “回归” 二字，但实际上是解决分类问题的一类线性模型。

##### 1.12. 随机梯度下降， SGD

随机梯度下降是拟合线性模型的一个简单而高效的方法。在样本量（和特征数）很大时尤为有用。 方法 `partial_fit` 可用于 online learning （在线学习）或基于 out-of-core learning （外存的学习）

[`SGDClassifier`](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.SGDClassifier.html#sklearn.linear_model.SGDClassifier) 和 [`SGDRegressor`](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.SGDRegressor.html#sklearn.linear_model.SGDRegressor) 分别用于拟合分类问题和回归问题的线性模型，可使用不同的（凸）损失函数，支持不同的罚项。 例如，设定 `loss="log"` ，则 [`SGDClassifier`](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.SGDClassifier.html#sklearn.linear_model.SGDClassifier) 拟合一个逻辑斯蒂回归模型，而 `loss="hinge"` 拟合线性支持向量机（SVM）。

