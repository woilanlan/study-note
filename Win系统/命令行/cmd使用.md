# cmd常用命令

```log
清空屏幕    cls
```

在CMD命令行中切换到管理员权限模式:

<https://blog.csdn.net/windymsth/article/details/78911310>

<https://blog.csdn.net/super__code/article/details/79613035>

## 基础知识

### 文件夹新建和删除

文件夹新建

```bat
md 盘符:\路径\新目录

md c:\test\newtest
```

注：使用cmd进入需要新建文件的根目录下，直接使用md或者mkdir直接创建文件夹

```bat
md newtest
mkdir newtest
```

删除文件夹

```bat
rd newtest
```

### 文件新建和删除

新建空文件

```bat
type nul>文件名

type nul> newtest.txt
```

新建非空文件

```bat
echo [文件内容]>文件名

echo "hello">a.txt
```

删除文件

```bat
del *.*

del newtest.txt
```
