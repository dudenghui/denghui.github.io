## Matplotlib使用指南

**`matplotlib`** 是一个 **`Python`** 的 `2D` 图形包。

### 使用 Pyplot

```python
import numpy as np
import matplotlib.pyplot as plt
```

`matplotlib.pyplot` 包含一系列类似 **`MATLAB`** 中绘图函数的相关函数。每个 `matplotlib.pyplot` 中的函数对当前的图像进行一些修改，例如：产生新的图像，在图像中产生新的绘图区域，在绘图区域中画线，给绘图加上标记，等等…… `matplotlib.pyplot` 会自动记住当前的图像和绘图区域，因此这些函数会直接作用在当前的图像上。

### 常用图表及适用范围

#### 常用图表

以下只给出绘制指定的图标所用的函数，关于接口参数参考[官方文档](https://matplotlib.org/tutorials/introductory/sample_plots.html),关于一些附加细节可参考文档也可参考学习笔记（jupyter notebook）

1. line线图plot()

   反映一维数据的变化趋势或者一个变量随另一个变量的变化

2. scatter散点图scatter()

   反映二维数据的分布，多涉及一些与位置相关的统计

3. hist直方图hist()

   

4. 柱状图bar()

5. pie饼状图pie()

6. image图片

7. 轮廓和伪色

8. path路径图

9. 三维图

10. stream流图 [`streamplot()`](https://matplotlib.org/api/_as_gen/matplotlib.pyplot.streamplot.html#matplotlib.pyplot.streamplot)

11. 椭圆图 [Phoenix](http://www.jpl.nasa.gov/news/phoenix/main.php) 

12. GUI widgets

13. Date handling时间序列

14. Log plots对数图

15. Polar plots极坐标图polar()

#### 小众图表：

1. 弦图[链接](https://zhuanlan.zhihu.com/p/67985078).

   ![弦图](https://pic2.zhimg.com/v2-9e08addaf1f92a8294c6691fe6559aa9_1200x500.jpg)

2. 

参考文章：

[你被柱状图骗了好多年！统计图表中的大坑！](https://zhuanlan.zhihu.com/p/43974249):主要意思是有时候使用柱状图会损失很多的信息，**描述数据，或者解读数据的时候，不能只关注其“集中性”和“离散性”指标（如均数、中位数、标准差、四分位数等），还得关注原始数据的分布形式。**在描述数据的时候有时偏重于使用“**小提琴图**”。











