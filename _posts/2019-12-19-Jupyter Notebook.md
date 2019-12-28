## Jupyter Notebook

[知乎文章](https://zhuanlan.zhihu.com/p/33105153)

### 介绍

> Jupyter Notebook是基于网页的用于交互计算的应用程序。其可被应用于全过程计算：开发、文档编写、运行代码和展示结果。——[Jupyter Notebook官方介绍](https://link.zhihu.com/?target=https%3A//jupyter-notebook.readthedocs.io/en/stable/notebook.html)

简而言之，Jupyter Notebook是以网页的形式打开，可以在网页页面中**直接编写代码**和**运行代码**，代码的**运行结果**也会直接在代码块下显示的程序。如在编程过程中需要编写说明文档，可在同一个页面中直接编写，便于作及时的说明和解释。

### **组成部分**

#### **网页应用**

网页应用即基于网页形式的、结合了编写说明文档、数学公式、交互计算和其他富媒体形式的工具。**简言之，网页应用是可以实现各种功能的工具。**

#### **文档**

即Jupyter Notebook中所有交互计算、编写说明文档、数学公式、图片以及其他富媒体形式的输入和输出，都是以文档的形式体现的。

这些文档是保存为后缀名为`.ipynb`的`JSON`格式文件，不仅便于版本控制，也方便与他人共享。

此外，文档还可以导出为：HTML、LaTeX、PDF等格式。

### **Jupyter Notebook的主要特点**

① 编程时具有**语法高亮**、*缩进*、*tab补全*的功能。

② 可直接通过浏览器运行代码，同时在代码块下方展示运行结果。

③ 以富媒体格式展示计算结果。富媒体格式包括：HTML，LaTeX，PNG，SVG等。

④ 对代码编写说明文档或语句时，支持Markdown语法。

⑤ 支持使用LaTeX编写数学性说明。

### 拓展功能

#### 1. 关联Jupyter Notebook和conda的环境和包

```text
conda install nb_conda
```

执行上述命令能够将你conda创建的环境与Jupyter Notebook相关联，便于你在Jupyter Notebook的使用中，在不同的环境下创建笔记本进行工作。

#### 2.**Markdown生成目录**

jupyter notebook必须添加插件才能使用目录功能

```text
conda install -c conda-forge jupyter_contrib_nbextensions
```

执行上述命令后，启动Jupyter Notebook，你会发现导航栏多了“Nbextensions”的类目，点击 “Nbextensions”，勾选“Table of Contents ⑵”，之后再在Jupyter Notebook中使用Markdown，点击下图的图标即可使用啦。

#### **3. Markdown在文中设置链接并定位**

在使用Markdown编辑文档时，难免会遇到需要在文中设定链接，定位在文档中的其他位置便于查看。因为Markdown可以完美的兼容html语法，因此这种功能可以通过html语法当中“a标签”的索引用法来实现。

语法格式如下：

```text
[添加链接的正文](#自定义索引词)
<a id=自定义索引词>跳转提示</a>
```

注意：

1. 1. 语法格式当中所有的符号均是**英文半角**。
   2. “自定义索引词”最好是英文，较长的词可以用下划线连接。
   3. “a标签”出现在想要被跳转到的文章位置，html标签除了单标签外均要符合“有头（``）必有尾（``）”的原则。头尾之间的“跳转提示”是可有可无的。
   4. “a标签”中的“id”值即是为正文中添加链接时设定的“自定义索引值”，这里通过“id”的值实现从正文的链接跳转至指定位置的功能。

#### **4. 加载指定网页源代码**

想在Jupyter Notebook中直接加载指定网站的源代码到笔记本中。执行以下命令:其中，URL为指定网站的地址。

```text
%load URL
```

#### **5. 加载本地Python文件**

想在Jupyter Notebook中加载本地的Python文件并执行文件代码。执行以下命令：

```text
%load Python文件的绝对路径
```

**注意：**

1. Python文件的后缀为“.py”。
2. “%load”后跟的是Python文件的**绝对路径**。
3. 输入命令后，可以按`CTRL 回车`来执行命令。第一次执行，是将本地的Python文件内容加载到单元格内。此时，Jupyter Notebook会自动将“%load”命令注释掉（即在前边加井号“#”），以便在执行已加载的文件代码时不重复执行该命令；第二次执行，则是执行已加载文件的代码。

#### **6. 直接运行本地Python文件**

不想在Jupyter Notebook的单元格中加载本地Python文件，想要直接运行。执行命令：

```text
%run Python文件的绝对路径
```

或

```text
!python3 Python文件的绝对路径
```

或

```text
!python Python文件的绝对路径
```

**注意**

1. Python文件的后缀为“.py”。
2. “%run”后跟的是Python文件的**绝对路径**。
3. “!python3”用于执行Python
   3.x版本的代码。
4. “!python”用于执行Python
   2.x版本的代码。
5. “!python3”和“!python”属于 `!shell命令` 语法的使用，即在Jupyter Notebook中执行shell命令的语法。
6. 输入命令后，可以按 `control return` 来执行命令，执行过程中将不显示本地Python文件的内容，直接显示运行结果。

#### **7. 获取当前位置**

想要在Jupyter Notebook中获取当前所在位置的**绝对路径。**

```text
%pwd
```

或

```text
!pwd
```

**注意**

1. 获取的位置是当前Jupyter Notebook中创建的笔记本所在位置，且该位置为**绝对路径**。
2. “!pwd”属于 `!shell命令` 语法的使用，即在Jupyter
   Notebook中执行shell命令的语法。

#### **8. 在Jupyter Notebook使用shell命令**

**方法一——在笔记本的单元格中**

```text
!shell命令
```

- 在Jupyter Notebook中的笔记本单元格中用英文感叹号“!”后接shell命令即可执行shell命令。

**方法二——在Jupyter Notebook中新建终端**

**启动方法**

在Jupyter Notebook主界面，即“File”界面中点击“New”；在“New”下拉框中点击“Terminal”即新建了终端。此时终端位置是在你的家目录，可以通过`pwd`命令查询当前所在位置的绝对路径。

**关闭方法**

在Jupyter Notebook的“Running”界面中的“Terminals”类目中可以看到正在运行的终端，点击后边的“Shutdown”即可关闭终端。





### **参考资料**

   1.知乎：jupyter notebook 可以做哪些事情？[猴子的回答](https://www.zhihu.com/question/46309360/answer/254638807?utm_source=wechat_session&utm_medium=social)

2. [Jupyter Notebook官方介绍](https://link.zhihu.com/?target=https%3A//jupyter-notebook.readthedocs.io/en/stable/notebook.html)

3. [Anaconda官方下载页面](https://link.zhihu.com/?target=https%3A//www.anaconda.com/download/%23macos)

4. [Python·Jupyter Notebook各种使用方法记录](https://link.zhihu.com/?target=http%3A//blog.csdn.net/tina_ttl/article/details/51031113%2321-%E6%96%B9%E5%BC%8F%E4%B8%80)

5. [Stack Overflow中有关如何隐藏/显示输入单元格的问题](https://link.zhihu.com/?target=https%3A//stackoverflow.com/questions/27934885/how-to-hide-code-from-cells-in-ipython-notebook-visualized-with-nbviewer)

6. [魔术命令官方文档](https://link.zhihu.com/?target=http%3A//ipython.readthedocs.io/en/stable/interactive/magics.html)

7. [Jupyter Notebook 的快捷键](https://link.zhihu.com/?target=http%3A//blog.csdn.net/lawme/article/details/51034543)

8. [Jupyter Notebook官方文档](https://link.zhihu.com/?target=http%3A//jupyter.org/documentation)