## Atom使用

### 快捷键

> ```python
> # 快捷键
> Ctrl + /                启用注释
> Ctrl + \                展示隐藏目录树
> Ctrl + Alt + I          打开Chrome调试器
> Ctrl + [                向右缩进
> Ctrl + ]                向左缩进
> Shift + Home            选定光标至行首
> Shift + End             选定光标至行尾
> Ctrl + D                匹配选定下一个
> Alt + F3                匹配选定所有
> Ctrl + up               选中行上移
> Ctrl + down             选中行下移
> 
> # 目录树操作
> a   添加文件
> d   将当前文件另存为
> i   显示(隐藏)版本控制忽略的文件
> 
> # 折叠
> Alt + Ctrl + [          折叠
> Alt + Ctrl + ]          展开
> Alt + Ctrl + Shift + {  折叠全部
> Alt + Ctrl + Shift + }  展开全部
> 
> # Markdown 写作
> Ctrl + Shift + M        Markdown预览
> 
> # Markdown 语法补全
> b, legal, img, l, i, code, t, table
> ```

### 常用插件

1、UI主题

- [atom-material-ui](https://link.zhihu.com/?target=https%3A//atom.io/themes/atom-material-ui) ，笔者使用的ui
- [atom-material-syntax](https://link.zhihu.com/?target=https%3A//atom.io/themes/atom-material-syntax)，和上面配套
- [seti-syntax](https://link.zhihu.com/?target=https%3A//atom.io/themes/seti-syntax)，亮点在文件的 icons

2、代码美化

- [file-icons](https://link.zhihu.com/?target=https%3A//atom.io/packages/file-icons)，显示文件类型对应的图标
- [atom-beautify](https://link.zhihu.com/?target=https%3A//atom.io/packages/atom-beautify)，支持大多数语言的代码格式化
- [activate-power-mode](https://link.zhihu.com/?target=https%3A//atom.io/packages/activate-power-mode)，这个叼，不过慎用
- [pigments](https://link.zhihu.com/?target=https%3A//atom.io/packages/pigments)，颜色提示
- [minimap](https://link.zhihu.com/?target=https%3A//atom.io/packages/minimap)，代码预览图

3、提升效率

- [autocomplete-paths](https://link.zhihu.com/?target=https%3A//atom.io/packages/autocomplete-paths)，补全路径，有用！
- [atom-ternjs](https://link.zhihu.com/?target=https%3A//atom.io/packages/atom-ternjs)，补全 JS
- [autocomplete-python](https://link.zhihu.com/?target=https%3A//atom.io/packages/autocomplete-python)，Python补全
- [emmet](https://link.zhihu.com/?target=https%3A//atom.io/packages/emmet)，超有名的前端工具
- [docblockr](https://link.zhihu.com/?target=https%3A//atom.io/packages/docblockr)，代码注释，可惜不支持Python
- [vim-mode](https://link.zhihu.com/?target=https%3A//atom.io/packages/vim-mode)，官方出品，在 Atom 上使用 Vim，哈哈哈
- [platformio-ide-terminal](https://link.zhihu.com/?target=https%3A//atom.io/packages/platformio-ide-terminal)，Atom 中集成终端，使用太顺畅了
- [markdown-writer](https://link.zhihu.com/?target=https%3A//atom.io/packages/markdown-writer)，markdown工具，便利

最后重点介绍一个插件，我们千辛万苦才配置好的 Atom，哪天电脑出了问题，需要重新安装配置 Atom，相信这个过程你一定不想来第二遍，所以我们的备份插件 [sync-settings](https://link.zhihu.com/?target=https%3A//atom.io/packages/sync-settings) 就闪亮登场了，它的配置不麻烦，但过程比较曲折，所以提出来详细说明：

首先需要在 GitHub 上获取两样东西，Access Token 和 Gist Id

![img](https://pic3.zhimg.com/80/v2-3b0e0c39dc6d1769319408074172a032_hd.png)

![img](https://pic2.zhimg.com/80/v2-e0aa06bfd09732aed83ae9d59f403aa1_hd.png)

然后将 Access Token 和 Gist Id 填入 插件的配置页面

![img](https://pic4.zhimg.com/80/v2-15afda85c0978298ce2526d01f32398f_hd.png)

使用快捷键 Ctrl + Shift + P 呼出命令栏，输入 sync backup，回车

![img](data:image/svg+xml;utf8,<svg xmlns='http://www.w3.org/2000/svg' width='680' height='486'></svg>)

最后会提示以下信息，那么恭喜你将自己的 Atom 所有信息都备份了，下次恢复备份只需要按照上一步输入 sync restore 就行了

![img](https://pic4.zhimg.com/80/v2-a793000dfeba01ad77a1fbdbea05bc03_hd.png)

以上就是笔者折腾 Atom 的全过程，其中插件的配置比较简单没有详细说明，大部分按照说明都可以完成。

# 总结

Atom 是一款现代化的文本编辑器，界面设计赏心悦目，让人在使用中神清气爽，优秀的第三方插件使其工作效率可以大大增强；但它的缺点也是非常明显的，性能和流畅度比之于 Vim 或 Sublime 还有待提高。对于 Atom，笔者的使用场景是做一些简单的代码编辑和 markdown 的编写，使用起来非常顺手，所以这里也推荐给各位， 祝好！













