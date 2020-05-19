## Python中NaN出现原因和解决方法





### [Python如何优雅地处理NaN](https://blog.csdn.net/lglfa/article/details/8056652)

很多数据不可避免的会遗失掉，或者采集的时候采集对象不愿意透露，这就造成了很多NaN（Not a Number）的出现。这些NaN会造成大部分模型运行出错，所以对NaN的处理很有必要。(基于pandas)

###### 1、简单粗暴地去掉

有如下dataframe，先用`df.isnull().sum()`检查下哪一列有多少NaN:

##### 将含有NaN的列(columns)去掉:

```
data_without_NaN =df.dropna(axis=1)
print (data_without_NaN)
```

###### 2、遗失值插补法

很多时候直接删掉列会损失很多有价值的数据，不利于模型的训练。所以可以考虑将NaN替换成某些数，显然不能随随便便替换，有人喜欢替换成0，往往会画蛇添足。譬如调查工资收入与学历高低的关系，有的人不想透露工资水平，但如果给这些NaN设置为0很显然会失真。所以Python有个Imputation（插补）的方法，其中 的算法不细究。代码如下：

```
from sklearn.preprocessing import Imputer

my_imputer = Imputer()
data_imputed = my_imputer.fit_transform(df)
print (type(data_imputed))
# array转换成df
df_data_imputed = pd.DataFrame(data_imputed,columns=df.columns)
print (df_data_imputed)
```

可以看出，这里大概是用平均值进行了替换。

###### 3、推广的遗失值插补法

这个推广的思想是NaN本身具有一定数据价值，譬如不爱说自己工资的被调查者是不是有什么共性，这个时候就不能简单的只用上面的插补法，要增加几列，将NaN的情况记录下来作为新的数据：

```
# 先复制一份爱怎么玩怎么玩
new_data = df.copy()

# 增加有NaN的布尔列（True/False）
cols_with_missing = (col for col in new_data.columns 
                                 if new_data[col].isnull().any())
for col in cols_with_missing:
    new_data[col + '_was_NaN'] = new_data[col].isnull()
print (new_data)

# Imputation
my_imputer = Imputer()
new_data_imputed = my_imputer.fit_transform(new_data)
# array转换成df
df_new_data_imputed = pd.DataFrame(new_data_imputed,columns=new_data.columns)
print (df_new_data_imputed)
```