# VSCode使用

官网：<https://code.visualstudio.com/>

在首页，点击下载，进行安装

新入手一款工具，首先要做的是搞明白各个菜单有什么用。所以千万不要被英语所阻挡。

1、安装中文语言包。

参考：<https://code.visualstudio.com/docs/getstarted/locales>

```c
Ctrl+Shift+X    打开扩展视图
category:"Language Packs"   查找对应语言包进行安装

Ctrl+Shift+P    打开命令面板
Configure Display Language  配置显示语言
locale.json     配置默认显示语言
    "locale":"zh-CN"    设置为简体中文
```

2、在帮助选项卡，查看使用文档

<https://code.visualstudio.com/docs#vscode>

<https://code.visualstudio.com/docs/getstarted/tips-and-tricks>

3、从控制台启动VSCode

在控制台输入```Code .```将在该文件夹中打开VS Code。安装程序会自动将VS Code添加到您的%PATH%环境变量中。

4、VS快捷键

进入欢迎页面 --> 帮助 --> 下载快捷键速查表

```c
Ctrl+P          快速打开文件
Ctrl+F4         关闭编辑器
Ctrl+K Ctrl+S   快捷键查询
Ctrl+K Ctrl+M   快捷键拓展
Ctrl+Shift+M    状态栏
F8或Shift+F8    循环检查错误

Ctrl+K Ctrl+T   改变主题
Ctrl+Shift+P    打开命令面板
    Preferences: Color Theme
    Preferences: File icon Theme

Ctrl+,          设置面板
    settings.json   配置设置文件

Ctrl+`          打开终端
Ctrl+B          隐藏或显示侧边栏
Ctrl+K Z        全屏模式（ESC 两次退出)
Ctrl+Shift+E    打开资源管理器窗口

Ctrl+Shift+P    打开命令面板
    Change File Encoding    更改文件编码
    Change Language Mode    更改语言模式
    View:Toggle Word Wrap   查看：切换自动换行
    File:Reveal in Explorer 在资源管理器中显示
    Terminal:Select Default Shell   选择默认shell

CTRL+K,M        更改语言模式
Alt+Z           查看：切换自动换行
Shift+Alt+R     在资源管理器中显示
```

5、编辑技巧

```c
多行编辑：
Alt+Click       任意位置添加游标
Ctrl+Alt+Up     在当前位置上方
Ctrl+Alt+Down   在当前位置下方
Ctrl+Shift+L    当前选中的所有匹配项
Ctrl+D          当前选中项的下一个匹配项
Shift+Alt       鼠标拖动选中块

Ctrl+I          选中当前行
Ctrl+Up/Down    选中多行
Alt+Up          向上移动当前行
Alt+Down        向下移动当前行
Shift+Alt+Up    复制到当前行上方
Shift+Alt+Down  复制到当前行上方

Ctrl+G          导航到指定行
Ctrl+Home       导航到文件开始
Ctrl+End        导航到文件结束

Ctrl+Shift+[    折叠代码
Ctrl+Shift+]    展开代码
Shift+Alt+Left  收缩选择（当前代码块）
Shift+Alt+Right 展开选择

Ctrl+K Ctrl+F   格式化当前选中代码
Shift+Alt+F     格式化当前文件
Ctrl+K Ctrl+X   取消行后的空白

Ctrl+Shift+O    转到文件中的符号
    @:          增加一个冒号对符号进行分组
Ctrl+T          转到符号（工作空间）

Ctrl+Shift+V    打开Markdown预览
Ctrl+K V        并排编辑和预览

Ctrl+Space      智能感知（代码提示）
Ctrl+Shift+F12  查看定义
F12或Ctrl+click 转到定义
Alt+Left或Go > Back     回到之前位置
Shift+F12       查看所有引用
F2              重命名（函数）
```

6、中文乱码

文件->首选项->设置->文本编辑器->文件：勾选Auto Guess Encoding

<https://jingyan.baidu.com/article/5552ef4792ac5a518ffbc996.html>

7、自动换行

文件->首选项->设置->编辑器，右侧把off换成on

8、sql使用入门

安装扩展：SQL Server(mssql)

```c
Ctrl+Shift+P    打开命令面板
    输入sql
```

<https://docs.microsoft.com/en-us/sql/linux/sql-server-linux-develop-use-vscode?view=sql-server-2017#create-or-open-a-sql-file>

9、应用调试

扩展：

Debugger for Chrome

<https://blog.csdn.net/xdcx950288/article/details/80640918>

<https://www.cnblogs.com/mxk-star/p/7279785.html>

## vscode工具

1、可以通过按Ctrl + Shift + O快速导航到文件中的相关CSS符号。

2、将鼠标悬停在选择器或属性上将提供与CSS规则匹配的HTML代码段。备注：并不会去引用中寻找，只是提示。

3、调试js的时候，可以直接在调试控制台打印输出。

4、切换行注释：Ctrl+/

5、工作区的定义：

<https://www.jianshu.com/p/25706af1f6a7>

6、如何让打开的文件不消失，双击打开。

"workbench.editor.enablePreview": false
"workbench.editor.enablePreviewFromQuickOpen": false

在设置直接搜索：editor.enablePreview 取消勾选。

7、如何使用tomcat来调试程序。

安装插件：Tomcat for Java
添加本地Tomcat
把项目生成war包
运行Tomcat

## 工作区

工作区是一个非常重要的概念。我们可以根据不同的开发要求，配置不同的工作区，安装对应的拓展，保持软件的轻量级和定制化。

在工作区中我们可以添加或移除文件夹，来打开不同的项目。同时保持文件的目录的组成。
