# Lombok使用

## 参考

[一份不可多得的 Lombok 学习指南](https://mp.weixin.qq.com/s/-4W5-fOK0sGSaNBktXA-YQ)

[Lombok 看这篇就够了](https://zhuanlan.zhihu.com/p/32779910)

[lombok踩坑与思考](https://www.cnblogs.com/wuyuegb2312/p/9750462.html)

## 一、Lombok 简介

Lombok 是一款 Java 开发插件，使得 Java 开发者可以通过其定义的一些注解来消除业务工程中冗长和繁琐的代码，尤其对于简单的 Java 模型对象（POJO）。在开发环境中使用 Lombok 插件后，Java 开发人员可以节省出重复构建，诸如 hashCode 和 equals 这样的方法以及各种业务对象模型的 accessor 和 toString 等方法的大量时间。对于这些方法，Lombok 能够在编译源代码期间自动帮我们生成这些方法，但并不会像反射那样降低程序的性能。

## 二、Lombok 安装

2.1 构建工具

Maven

在 Maven 项目的 pom.xml 文件中添加 Lombok 依赖：

```xml
<dependency>
    <groupId>org.projectlombok</groupId>
    <artifactId>lombok</artifactId>
    <version>1.18.10</version>
    <scope>provided</scope>
</dependency>
```

2.2 IDEA 中安装 lombok 插件

打开 IDEA 的 Settings 面板 >> 选择 Plugins 选项 >> 在输入框输入”lombok” >> 点击安装 >> 提示重启 IDEA，安装成功

## 三、Lombok 详解

使用：在实体类上引入相关的注解

### @Getter and @Setter

自动生成默认的 getter/setter 方法。

### Constructor Annotations

使用 @NoArgsConstructor 注解可以为指定类，生成默认的构造函数

```java
//若设置 staticName 属性，将会生成一个私有的构造函数且生成一个staticName指定的静态方法
@NoArgsConstructor(staticName = "getInstance")
public class NoArgsConstructorDemo {
    private long id;
    private String name;
    private int age;
}
```

使用 @AllArgsConstructor 注解可以为指定类，生成包含所有成员的构造函数

使用 @RequiredArgsConstructor 注解可以为指定类必需初始化的成员变量，如 final 成员变量，生成对应的构造函数

### @EqualsAndHashCode

为指定类生成 equals 和 hashCode 方法

### @ToString

为指定类生成 toString 方法

### @Data

@Data 注解与同时使用以下的注解的效果是一样的：

```java
@ToString
@Getter
@Setter
@RequiredArgsConstructor
@EqualsAndHashCode
```

### @Log

若你将 @Log 的变体放在类上（适用于你所使用的日志记录系统的任何一种）；之后，你将拥有一个静态的 final log 字段，然后你就可以使用该字段来输出日志。

```java
@Log
private static final java.util.logging.Logger log = java.util.logging.Logger.getLogger(LogExample.class.getName());
@Log4j
private static final org.apache.log4j.Logger log = org.apache.log4j.Logger.getLogger(LogExample.class);
@Log4j2
private static final org.apache.logging.log4j.Logger log = org.apache.logging.log4j.LogManager.getLogger(LogExample.class);
@Slf4j
private static final org.slf4j.Logger log = org.slf4j.LoggerFactory.getLogger(LogExample.class);
@XSlf4j
private static final org.slf4j.ext.XLogger log = org.slf4j.ext.XLoggerFactory.getXLogger(LogExample.class);
@CommonsLog
private static final org.apache.commons.logging.Log log = org.apache.commons.logging.LogFactory.getLog(LogExample.class);
```

### @Synchronized

@Synchronized 是同步方法修饰符的更安全的变体。与 synchronized 一样，该注解只能应用在静态和实例方法上。它的操作类似于 synchronized 关键字，但是它锁定在不同的对象上。

synchronized 关键字应用在实例方法时，锁定的是 this 对象，而应用在静态方法上锁定的是类对象。对于 @Synchronized 注解声明的方法来说，它锁定的是 LOCK 或 lock

### @Builder

使用 @Builder 注解可以为指定类实现建造者模式，该注解可以放在类、构造函数或方法上

### @SneakyThrows

@SneakyThrows 注解用于自动抛出已检查的异常，而无需在方法中使用 throw 语句显式抛出。

### @NonNull

在方法或构造函数的参数上使用 @NonNull 注解，它将会为你自动生成非空校验语句

### @Clean

@Clean 注解用于自动管理资源，用在局部变量之前，在当前变量范围内即将执行完毕退出之前会自动清理资源，自动生成 try-finally 这样的代码来关闭流。

```java
public class CleanupDemo {
    public static void main(String[] args) throws IOException {
        @Cleanup InputStream in = new FileInputStream(args[0]);
        @Cleanup OutputStream out = new FileOutputStream(args[1]);
        byte[] b = new byte[10000];
        while (true) {
            int r = in.read(b);
            if (r == -1) break;
            out.write(b, 0, r);
        }
    }
}
```

### @With

在类的字段上应用 @With 注解之后，将会自动生成一个 withFieldName(newValue) 的方法，该方法会基于 newValue 调用相应构造函数，创建一个当前类对应的实例。
