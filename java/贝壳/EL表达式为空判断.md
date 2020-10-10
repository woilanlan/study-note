# EL表达式为空判断

[el表达式null和空的判断](https://blog.csdn.net/sd4015700/article/details/18445859)

```jsp
El表达式判断是否为空字符串

${empty 值}  返回true ,表示为空字符串;

<c:if test=" ${empty  chapterlist} ">
<td>青蛙，是个笨蛋！！！</td>
</c:if>


El表达式判断是否为空

${值 eq  null } 返回true 的话，表示为空

<c:if test="${chapterlist eq  null }">
<td>青蛙，是个笨蛋！！！</td>
</c:if>
```

[java 对象、集合的非空判断](https://www.cnblogs.com/xxyfhjl/p/3974486.html)

对象验证是否不为空: if( null != obj )
List验证不为空：if( null != list && list.size() > 0 )
Map验证不为空：if( null != map && map.size() > 0 )
