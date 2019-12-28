## Pycharm使用



### PEP8标准

PEP8是 Python Enhancement Proposal 8的缩写，翻译过来就是 Python增强建议书，也就是Python编码规范。例如：缩进，注释，行限字数，每行之间的空行，空格的使用等。好的代码，它的书写会遵循代码的规范。但是对于初学者来说，在写代码的同时还要记住代码规范，似乎显得有些困难。之前说过PyCharm是个功能强大的IDE，所以它也提供了为初学者解决代码规范的方法。我们需要在环境中安装 autopep8这个工具

> pip install autopep8

### 快捷键

> **1、编辑（Editing）**
> Ctrl + Space 基本的代码完成（类、方法、属性）
> Ctrl + Alt + Space 快速导入任意类
> Ctrl + Shift + Enter 语句完成
> Ctrl + P 参数信息（在方法中调用参数）
> Ctrl + Q 快速查看文档
> Shift + F1 外部文档
> Ctrl + 鼠标 简介
> Ctrl + F1 显示错误描述或警告信息
> Alt + Insert 自动生成代码
> Ctrl + O 重新方法
> Ctrl + Alt + T 选中
> Ctrl + / 行注释
> Ctrl + Shift + / 块注释
> Ctrl + W 选中增加的代码块
> Ctrl + Shift + W 回到之前状态
> Ctrl + Shift + ]/[ 选定代码块结束、开始
> Alt + Enter 快速修正
> Ctrl + Alt + L 代码格式化
> Ctrl + Alt + O 优化导入
> Ctrl + Alt + I 自动缩进
> Tab / Shift + Tab 缩进、不缩进当前行
> Ctrl+X/Shift+Delete 剪切当前行或选定的代码块到剪贴板
> Ctrl+C/Ctrl+Insert 复制当前行或选定的代码块到剪贴板
> Ctrl+V/Shift+Insert 从剪贴板粘贴
> Ctrl + Shift + V 从最近的缓冲区粘贴
> Ctrl + D 复制选定的区域或行
> Ctrl + Y 删除选定的行
> Ctrl + Shift + J 添加智能线
> Ctrl + Enter 智能线切割
> Shift + Enter 另起一行
> Ctrl + Shift + U 在选定的区域或代码块间切换
> Ctrl + Delete 删除到字符结束
> Ctrl + Backspace 删除到字符开始
> Ctrl + Numpad+/- 展开折叠代码块
> Ctrl + Numpad+ 全部展开
> Ctrl + Numpad- 全部折叠
> Ctrl + F4 关闭运行的选项卡
>
> **2、查找/替换(Search/Replace)**
> F3 下一个
> Shift + F3 前一个
> Ctrl + R 替换
> Ctrl + Shift + F 全局查找
> Ctrl + Shift + R 全局替换
>
> **3、运行(Running)**
> Alt + Shift + F10 运行模式配置
> Alt + Shift + F9 调试模式配置
> Shift + F10 运行
> Shift + F9 调试
> Ctrl + Shift + F10 运行编辑器配置
> Ctrl + Alt + R 运行manage.py任务
>
> **4、调试(Debugging)**
> F8 跳过
> F7 进入
> Shift + F8 退出
> Alt + F9 运行游标
> Alt + F8 验证表达式
> Ctrl + Alt + F8 快速验证表达式
> F9 恢复程序
> Ctrl + F8 断点开关
> Ctrl + Shift + F8 查看断点
>
> **5、导航(Navigation)**
> Ctrl + N 跳转到类
> Ctrl + Shift + N 跳转到符号
> Alt + Right/Left 跳转到下一个、前一个编辑的选项卡
> F12 回到先前的工具窗口
> Esc 从工具窗口回到编辑窗口
> Shift + Esc 隐藏运行的、最近运行的窗口
> Ctrl + Shift + F4 关闭主动运行的选项卡
> Ctrl + G 查看当前行号、字符号
> Ctrl + E 当前文件弹出
> Ctrl+Alt+Left/Right 后退、前进
> Ctrl+Shift+Backspace 导航到最近编辑区域
> Alt + F1 查找当前文件或标识
> Ctrl+B / Ctrl+Click 跳转到声明
> Ctrl + Alt + B 跳转到实现
> Ctrl + Shift + I查看快速定义
> Ctrl + Shift + B跳转到类型声明
> Ctrl + U跳转到父方法、父类
> Alt + Up/Down跳转到上一个、下一个方法
> Ctrl + ]/[跳转到代码块结束、开始
> Ctrl + F12弹出文件结构
> Ctrl + H类型层次结构
> Ctrl + Shift + H方法层次结构
> Ctrl + Alt + H调用层次结构
> F2 / Shift + F2下一条、前一条高亮的错误
> F4 / Ctrl + Enter编辑资源、查看资源
> Alt + Home显示导航条F11书签开关
> Ctrl + Shift + F11书签助记开关
> Ctrl + #[0-9]跳转到标识的书签
> Shift + F11显示书签
>
> **6、搜索相关(Usage Search)**
> Alt + F7/Ctrl + F7文件中查询用法
> Ctrl + Shift + F7文件中用法高亮显示
> Ctrl + Alt + F7显示用法
>
> **7、重构(Refactoring)**
> F5复制F6剪切
> Alt + Delete安全删除
> Shift + F6重命名
> Ctrl + F6更改签名
> Ctrl + Alt + N内联
> Ctrl + Alt + M提取方法
> Ctrl + Alt + V提取属性
> Ctrl + Alt + F提取字段
> Ctrl + Alt + C提取常量
> Ctrl + Alt + P提取参数
>
> **8、控制VCS/Local History**
> Ctrl + K提交项目
> Ctrl + T更新项目
> Alt + Shift + C查看最近的变化
> Alt + BackQuote(’)VCS快速弹出
>
> **9、模版(Live Templates)**
> Ctrl + Alt + J当前行使用模版
> Ctrl +Ｊ插入模版
>
> **10、基本(General)**
> Alt + #[0-9]打开相应的工具窗口
> Ctrl + Alt + Y同步
> Ctrl + Shift + F12最大化编辑开关
> Alt + Shift + F添加到最喜欢
> Alt + Shift + I根据配置检查当前文件
> Ctrl + BackQuote(’)快速切换当前计划
> Ctrl + Alt + S　打开设置页
> Ctrl + Shift + A查找编辑器里所有的动作
> Ctrl + Tab在窗口间进行切换

![img](https://pic3.zhimg.com/80/v2-c6c787587d45e60ac259eb7a1758560a_hd.jpg)

### 其他

[有关插件](https://zhuanlan.zhihu.com/p/98096152)





##### VIM（Unix及类Unix文本编辑器）

Vim是一个类似于[Vi](https://baike.baidu.com/item/Vi/8987313)的著名的功能强大、高度可定制的[文本编辑器](https://baike.baidu.com/item/文本编辑器/8853160)，在Vi的基础上改进和增加了很多特性。VIM是[自由软件](https://baike.baidu.com/item/自由软件/405190)。Vim普遍被推崇为类[Vi编辑器](https://baike.baidu.com/item/Vi编辑器)中最好的一个，事实上真正的劲敌来自Emacs的不同变体。1999 年[Emacs](https://baike.baidu.com/item/Emacs)被选为Linuxworld文本编辑分类的优胜者，Vim屈居第二。但在2000年2月Vim赢得了Slashdot Beanie的最佳[开放源代码](https://baike.baidu.com/item/开放源代码/114160)文本编辑器大奖，又将Emacs推至二线， 总的来看， Vim和Emacs在文本编辑方面都是非常优秀的。













