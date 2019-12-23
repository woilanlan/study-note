# mysql安装

账号：root/Longlong

mysql在windows上有两种安装方式：安装引导程序安装和压缩包方式安装。

注意：

使用引导程序安装的话，选择自定义安装，选择要安装的组件，点击修改安装路径。
使用压缩包方式安装，注意my.ini文件的配置。
可以先使用引导程序安装，之后使用压缩包的方式进行配置。

## 连接mysql

```sh
# 连接数据库
sudo mysql -h 127.0.0.1 -u yh_admuser -p

# 查看当前有多少库
show databases;

# 查看数据库的创建细节
show create database ZHY1YHOATDB1;

# 选择一个数据库
use ZHY1YHOATDB1;

# 查看当前使用的是哪个库
select database();

# 查看当前库中的所有表
show tables;

# 查看表结构
desc BO_EU_SEAL;

# 数据库备份
mysqldump -h 127.0.0.1 -u yh_admuser -p test > test.sql;
```

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

```log
//北京时间东八区
serverTimezone=GMT%2B8 
//或者使用上海时间
serverTimezone=Asia/Shanghai
```

## 关闭开机启动

1.打开服务列表

有两种方法，一是快捷键 win+R 输入services.msc，二是右击我的电脑->管理->点击左侧服务和应用程序->服务

2.在服务列表里找到MySQL，在右键属性里面将启动类型自动改为手动

## mysql插入数据后返回自增ID的方法

```sql
SELECT LAST_INSERT_ID();
```

参考：<https://blog.csdn.net/zhuchunyan_aijia/article/details/93620357>
