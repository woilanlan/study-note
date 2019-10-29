# svn切换账号

## tortoisesvn客户端清除：

右键->tortoisesvn->setting

在弹出的settings窗口右侧，点击“Saved Data”,点击左侧的“Authentication”后方的“clear”按钮即可

## 删除对应文件

[如何清除Eclipse中的SVN账号信息](https://www.cnblogs.com/chenmingjun/p/9945668.html)

1、查看你的Eclipse中使用的是什么SVN Interface(svn接口)

Windows --> Preferences --> Team --> SVN

在右边的设置面板中可以看到【SVN Interface】或中文的【SVN接口】一栏，Client的选项框中显示的就是你当前用的SVN接口。

2、如果是用的JavaHL，找到以下目录：

win10~win7系统：C:\Users\"你的用户名"\AppData\Roaming\Subversion\ 会看到有一个auth目录，删除auth目录中的相关文件。

xp系统：C:\Documents and Settings\"你的用户名"\Application Data\Subversion\ 会看到有一个auth目录，删除auth目录中的相关文件。

注意：AppData一般隐藏了，文件资源管理器 -> 查看 -> 隐藏的项目，进行勾选。
