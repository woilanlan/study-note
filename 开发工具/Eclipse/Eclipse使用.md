# Eclipse使用

简书总结：<https://www.jianshu.com/p/482a8792b87b>

- 给函数添加注解：/** + 回车
- 添加/删除注释：Ctrl + Shift + /       Ctrl + Shift + \
- 上移某一行：Alt + ↑
- 选中当前行：Shift + ↑
- 代码提示：Alt + /
- 多行缩进/回退：Tab    Shift + Tab
- 文本转换为大写：Ctrl + Shift + X
- 查看类的层次结构：Ctrl + T
- 查找或替换：Ctrl + F
- 删除当前行：Ctrl + D
- 查找类：Ctrl + Shift + T

## 问题整理

### 1、Eclipse如何引入一个新的jar包？

Dynamic Web Project项目直接放到WEB-INF/lib文件夹下。

Java Project项目

- 在项目名上右击，New --> Floder --> 输入文件夹名称lib，点击OK
- 复制要引入的jar包到lib文件夹
- 在jar包上右键 --> Build Path --> Add to Build Path

参考：<https://jingyan.baidu.com/article/ca41422fc76c4a1eae99ed9f.html>

### 2、Eclipse如何查看一个类或方法的源码？

按住键盘ctrl键鼠标选择你想要查看源码的类或者方法名。

参考：<https://jingyan.baidu.com/article/0f5fb09904ef056d8334ea23.html>

### 3、Eclipse如何将指定代码转为一个方法。

选中代码 -->右键 -->Refactor(重构) -->Extract Method(提取方法) -->输入方法名称

### 4、Eclipse编辑HTML时如何关闭视图窗口？

Window --> Preferences --> General --> Editors --> File Associations --> HTML --> HTML Editor --> Default

参考：<https://blog.csdn.net/Rodge_Rom/article/details/78828979>

### 5、编码格式：

Window-->Preferences-->General

- 提高MyEclipse的打开速度
- Editors-->File Assosiations右边File types选择*.JSP在下方Associated editors:选择MyEclipse JSP Editor
- 更改编码格式(文件打开中文乱码)
- Content Types-->Text-->JSP选中*.jsp(locked)在下方输入utf-8点击Update
- Workspace右侧Text file encoding选择Other:UTF-8

建立新文件的编码格式：

- MyEcipse-->Files and Editors-->JSP右边Encoding:UTF-8
- Web-->JSP Files-->右边Encoding设置为ISO 10646/Unicode(UTF-8)，点击OK

参考：<https://zhidao.baidu.com/question/1703424180224829700.html>

### 6、使用Eclipse写JSP如何自动倒包。

在刚写完类名后敲 ```alt+/```

```java
Person(alt+/) person = new Person();
```

### 7、打包生成自己的标签库：

- 当前工程右键 --> Export --> java --> JAR file --> Next -->
- 选中src/com.itheima.example --> 选择保存路径：myjstl.jar --> Finish
- 然后把h.tld文件放到myjstl.jar\META-INF\目录下

### 8、MyEclipsse如何导入新的项目（程序内复制和引入新项目）

- 打开myeclipse找到File --> Import
- 选择General --> Existing Projects into Workspace，（要确认你的项目中存在.project文件）
- 点击Next，选择Browser，根据需要导入项目的路径，选择需要导入的项目，点击Finish
- 选中项目右键 -->properties --> myeclipse --> web --> context root --> 修改为新的项目名称。

<https://jingyan.baidu.com/article/63f2362845373f0208ab3db7.html>

#### 8.1、Eclipse中如何复制一个Java Web项目

选中项目复制 --> 点击粘贴 --> 输入新的项目名称 --> finish

选中项目右键 --> Properties --> Web Project Settings --> context root --> 修改为新的项目名称。

#### 8.2、Eclipse中怎么修改所复制的web项目的部署名字

点击Window --> Show View --> Navigator，
在Navigator窗口中，找到项目中的.setting文件夹下的org.eclipse.wst.common.component.xml文件

修改对应的项目名称：

```xml
<?xml version="1.0" encoding="UTF-8"?><project-modules id="moduleCoreId" project-version="1.5.0">
    <wb-module deploy-name="项目名称">
        <wb-resource deploy-path="/" source-path="/WebRoot" tag="defaultRootSource"/>
        <wb-resource deploy-path="/WEB-INF/classes" source-path="/src"/>
        <property name="java-output-path" value="/day15_01_regist/build/classes"/>
        <property name="context-root" value="项目名称"/>
    </wb-module>
</project-modules>
```

<https://blog.csdn.net/u012660464/article/details/53642269>

### 9、如何将MyEclipse项目导入eclipse

<https://www.cnblogs.com/skyblue-li/p/5972035.html>

### 10、在Eclipse中创建的新项目没有src文件的解决办法

Window---Preferences---java---Build Path---点击Folders

### 11、Eclipse中实现JS代码提示功能

安装AngularJS Eclipse 插件，在右击项目 --> configure --> convert AngularJS Project

### 12、Eclipse的WorkingSet使用

参考：<https://www.cnblogs.com/LiuChunfu/p/5860558.html>

---

- Chrome浏览器
- 刷新(清除缓存)：Ctrl + F5