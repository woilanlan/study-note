# maven工程的依赖

maven核心是对jar包的管理

## 实例

1、新建Java项目：day46_01_mavenHelloFriend

2、按照约定，新建Source Folder

- src/main/java
- src/main/resources
- src/test/java
- src/test/resources

3、新建包：com.itheima.maven

4、新建类：

HelloFriend.java

```java
package com.itheima.maven;

public class HelloFriend {
    public void showHelloFriend(){
        //报错
        Hello hello = new Hello();
        hello.sayHello();
    }
}
```

HelloFriendTest.java

```java
package com.itheima.maven;

public class HelloFriendTest {
    public static void main(String[] args) {
        HelloFriend helloFriend = new HelloFriend();
        helloFriend.showHelloFriend();
    }
}
```

5、新建pom.xml文件

```xml
<?xml version="1.0" encoding="UTF-8"?>

<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
  xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  <modelVersion>4.0.0</modelVersion>
  
  <groupId>com.itheima.maven</groupId>
  <artifactId>HelloFriend</artifactId>
  <version>1.0-SNAPSHOT</version>
  
  <dependencies>
    <!-- 声明依赖关系 -->
    <dependency>
        <groupId>com.itheima.maven</groupId>
        <artifactId>Hello</artifactId>
        <version>0.0.1-SNAPSHOT</version>
    </dependency>
  </dependencies>
</project>
```

6、编译项目

前提：day46_00_mavenHello项目必须使用mvn install将Hello-0.0.1-SNAPSHOT.jar部署到本地仓库，否则项目会报错。

```log
//进入工程目录
cd D:\java\longlong\day46_01_mavenHelloFriend

//直接部署
mvn install
```

## 拓展：分析整合三大框架后的jar包管理

通过依赖关系，借助仓库的概念，实现了相关联jar包的导入。
