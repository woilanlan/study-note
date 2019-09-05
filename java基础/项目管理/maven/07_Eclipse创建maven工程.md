# Eclipse创建maven工程

1、选择File -- New -- Maven Project，开始创建Maven项目

![创建Maven项目](资料/0701.png)

- 创建一个简单的项目，跳过原型选择。
- 使用默认的物理工作空间，右边点开可以更改
- 添加项目到指定的工作集中（包含多个项目的集合）

2、选择要创建的Maven项目原型(骨架)

![项目原型](资料/0702.png)

3、输入创建Maven项目所必须的参数

![Maven参数](资料/0703.png)

4、更改Maven项目中使用的jre

![打开右键菜单](资料/0704.png)

![更改JRE](资料/0705.png)

5、补充缺少的resources目录

新建Source Folder

- src/main/resources
- src/test/resources

6、更改pom.xml文件中的junit依赖

![调整junit版本](资料/0706.png)

7、简单测试

![测试](资料/0707.png)

8、在maven中进行编译，测试

选中项目 -- 右键 -- Run As -- Maven Test

![测试2](资料/0708.png)

## 参考

<https://blog.csdn.net/sky198989/article/details/81197627>

<https://www.cnblogs.com/shushengyou/p/8471519.html>

<https://www.cnblogs.com/sunddenly/p/4341542.html>