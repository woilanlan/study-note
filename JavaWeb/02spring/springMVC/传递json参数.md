# 传递json数据

参考：

[@RequestBody的使用](https://blog.csdn.net/justry_deng/article/details/80972817)

[application/x-www-form-urlencoded与application/json](https://blog.csdn.net/java_xxxx/article/details/81205315)

## 请求的格式

application/x-www-form-urlencoded

窗体数据被编码为名称/值对。这是标准的编码格式

multipart/form-data

窗体数据被编码为一条消息，页上的每个控件对应消息中的一个部分。

text/plain

窗体数据以纯文本形式进行编码，其中不含任何控件或格式字符。

application/json

- 前端提交的数据是json格式的字符串，后端要用@requestbody注解来接收
- @RequestBody接收请求体中的json数据；不加注解接收URL中的数据并组装为对象
