# mysql安装

账号：root/Longlong

mysql在windows上有两种安装方式：安装引导程序安装和压缩包方式安装。

注意：

使用引导程序安装的话，选择自定义安装，选择要安装的组件，点击修改安装路径。
使用压缩包方式安装，注意my.ini文件的配置。
可以先使用引导程序安装，之后使用压缩包的方式进行配置。

## 创建数据库和表

```sql
create database test;

CREATE TABLE `test`.`user` (
  `id` INT NOT NULL AUTO_INCREMENT,
  `username` VARCHAR(45) NULL,
  `address` VARCHAR(45) NULL,
  PRIMARY KEY (`id`))
ENGINE = InnoDB
DEFAULT CHARACTER SET = utf8mb4;

INSERT INTO `test`.`user` (`username`, `address`) VALUES ('longlong', 'woilanlan.github.io');
```

## 时间

[MySQL日期，字符串，时间戳互转](https://www.cnblogs.com/jhy-ocean/p/5560857.html)

[MySQL修改时区的方法小结](https://www.jb51.net/article/84198.htm)

spring.datasource.type=com.alibaba.druid.pool.DruidDataSource
spring.datasource.username=root
spring.datasource.password=xuelong
spring.datasource.url=jdbc:mysql://127.0.0.1:3306/test?characterEncoding=UTF-8&useSSL=false&useUnicode=true&serverTimezone=UTC

## 关闭开机启动

1.打开服务列表

有两种方法，一是快捷键 win+R 输入services.msc，二是右击我的电脑->管理->点击左侧服务和应用程序->服务

2.在服务列表里找到MySQL，在右键属性里面将启动类型自动改为手动