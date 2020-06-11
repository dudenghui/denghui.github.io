## 什么是伪随机数？

> 伪随机数是用确定性的算法计算出来自[0,1]均匀分布的随机数序列。并不真正的随机，但具有类似于随机数的统计特征，如均匀性、独立性等。在计算伪随机数时，若使用的初值（种子）不变，那么伪随机数的数序也不变。伪随机数可以用计算机大量生成，在模拟研究中为了提高模拟效率，一般采用伪随机数代替真正的随机数。模拟中使用的一般是循环周期极长并能通过随机数检验的伪随机数，以保证计算结果的随机性。--[百度百科]([https://baike.baidu.com/item/%E4%BC%AA%E9%9A%8F%E6%9C%BA%E6%95%B0/104358?fr=aladdin](https://baike.baidu.com/item/伪随机数/104358?fr=aladdin))

[伪随机数生成算法](https://www.cnblogs.com/shine-lee/p/9516757.html)

## 什么是伪随机数种子？

随机数种子（random seed）是指在伪随机数生成器中用于生成伪随机数的初始数值。对于一个伪随机数生成器，从相同的随机数种子出发，可以得到相同的随机数序列。随机数种子通常由当前计算机状态确定，如当前的时间。

## 关于Random中的随机数种子Seed

　　Random初始化的时候，可以以一个INT32作为参数，称为seed，MSDN上的解释是：“伪随机数是以相同的概率从一组有限的数字中选取的随机数的生成是从种子值开始”

　　所有标准库提供的Random函数其实都是假Random，提供的随机数也是伪随机数，真正的Random函数式不需要Seed的。所谓假Random，是指所返回的随机数字其实是一个稳定算法所得出的稳定结果序列，而不是真正意义上的随机序列。 Seed就是这个算法开始计算的第一个值。所以就会出现只要seed是一样的，那么后续所有“随机”结果和顺序也都是完全一致的。 通常情况下，你可以用 DateTime.Now.Millisecend() 也就是当前始终的毫秒来做Seed .因为毫秒对你来说是一个1000以内的随即数字。 这样可以大大改善保准库的Random结果的随机性。 不过这仍然算不上是完全随机，因为重复的概率还是千分之一。

　　需要注意的是，如果一直调用标准库Random，那么在调用了N次以后，输出结果就会循环最开始的序列了。也就是说，标准库Random所能生成的不同结果的个数也是有限的。32位系统一般也就是几万次以后就会出现重复。可以到网上找一个真正的随机函数，以替换标准库Random。

numpy.random多次运行结果一样：

```python
import numpy as np

np.random.seed(0)
print(np.random.rand(2))
print(np.random.rand(2))
np.random.seed(0)
print(np.random.rand(2))
print(np.random.rand(2))
```

python自带的random也有一样的效果：

```python
import random
random.seed(0)

print("1: ", random.random())
random.seed(0)
print("2: ", random.random())
print("3: ", random.random())
random.seed(0)
print("5: ", random.random())
print("6: ", random.random())
```

## Numpy中random模块的使用

[官方文档](https://numpy.org/devdocs/reference/random/index.html?highlight=random#module-numpy.random)

numpy中random模块的作用包含以下几个方面：

1. 生成一定范围的随机数，例如random(),randint(),choice()等
2. 对已有的数列随机打乱,例如shuffle()
3. 生成满足一定分布的随机数,例如beta(a, b, size)，伯努利分布binomial(n, p, size)

[链接](https://numpy.org/doc/1.18/reference/random/generator.html#numpy.random.Generator)

[链接](https://blog.csdn.net/weixin_42029738/article/details/81977492)

### Simple random data(numpy.random moudle)

1. integers(low[, high, size, dtype, endpoint](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/)):Return random integers from low (inclusive) to high (exclusive), or if endpoint=True, low (inclusive) to high (inclusive).

2. randint(low,high,size):return a random array with a "size" shape

3. random([size, dtype, out](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/)):Return random floats in the half-open interval [0.0, 1.0).

4. choice():choice(a, size=None, replace=True, p=None, axis=0):

   解释：从一维array a 或 int 数字a 中，以概率p随机选取大小为size的数据

   参数：

   - replace：表示是否重用元素，默认为true（抽取出来的数据有重复）
   - p:代表a中个元素被抽取的概率，注意其和为1

5. bytes(length):Return random bytes.

6. randn(d0, d1, …, dn)是从标准正态分布中返回一个或多个样本值

   参数为形状

7. rand(d0, d1, …, dn)的随机样本位于[0, 1)中

```python
a =  [1,2,3,4,5,6]
b = np.random.choice(a, 5)#在a数组中抽取6个数，replace为true
print(b)
c = np.random.choice(a,5,replace=False)
print(c)
d = np.random.choice(a, 5, replace=True, p=[0.5, 0.3, 0.2, 0., 0., 0.])#p是数组a中所有数出现的概率，总和为1
print(d)
```

### Permutations（打乱）

1. shuffle(x[, axis](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))：Modify a sequence in-place by shuffling its contents.

   解释：对数组x在axis轴上进行打乱

   Returns:None

2. permutation(x[, axis](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))：Randomly permute a sequence, or return a permuted range.

```python
rng = np.random.default_rng()
arr = np.arange(9)
rng.shuffle(arr)
print(arr)

arr = np.arange(9).reshape((3, 3))
rng.shuffle(arr)#默认axis=0
print(arr)

arr = np.arange(9).reshape((3, 3))
rng.shuffle(arr, axis=1)
print(arr)
```

### Distributions

beta(a, b[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))：Draw samples from a Beta distribution.

binomial(n, p[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a binomial distribution.

chisquare(df[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a chi-square distribution.

dirichlet(alpha[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from the Dirichlet distribution.

exponential([scale, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from an exponential distribution.

f(dfnum, dfden[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from an F distribution.

gamma(shape[, scale, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a Gamma distribution.

geometric(p[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from the geometric distribution.

gumbel([loc, scale, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a Gumbel distribution.

hypergeometric(ngood, nbad, nsample[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a Hypergeometric distribution.

laplace([loc, scale, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from the Laplace or double exponential distribution with specified location (or mean) and scale (decay).

logistic([loc, scale, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a logistic distribution.

lognormal([mean, sigma, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a log-normal distribution.

logseries(p[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a logarithmic series distribution.

multinomial(n, pvals[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a multinomial distribution.

multivariate_hypergeometric(colors, nsample)Generate variates from a multivariate hypergeometric distribution.

multivariate_normal(mean, cov[, size, …](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw random samples from a multivariate normal distribution.

negative_binomial(n, p[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a negative binomial distribution.

noncentral_chisquare(df, nonc[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a noncentral chi-square distribution.

noncentral_f(dfnum, dfden, nonc[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from the noncentral F distribution.

normal([loc, scale, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw random samples from a normal (Gaussian) distribution.

pareto(a[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a Pareto II or Lomax distribution with specified shape.

poisson([lam, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a Poisson distribution.

power(a[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draws samples in [0, 1](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/) from a power distribution with positive exponent a - 1.

rayleigh([scale, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a Rayleigh distribution.

standard_cauchy([size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a standard Cauchy distribution with mode = 0.

standard_exponential([size, dtype, method, out](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from the standard exponential distribution.

standard_gamma(shape[, size, dtype, out](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a standard Gamma distribution.

standard_normal([size, dtype, out](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a standard Normal distribution (mean=0, stdev=1).

standard_t(df[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a standard Student’s t distribution with df degrees of freedom.

triangular(left, mode, right[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from the triangular distribution over the interval [left, right](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/).

uniform([low, high, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a uniform distribution.

vonmises(mu, kappa[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a von Mises distribution.

wald(mean, scale[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a Wald, or inverse Gaussian, distribution.

weibull(a[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a Weibull distribution.

zipf(a[, size](vscode-resource://file///c%3A/Users/12569/Documents/Python_program/Python编程及其库/Numpy的使用方法/))Draw samples from a Zipf distribution.