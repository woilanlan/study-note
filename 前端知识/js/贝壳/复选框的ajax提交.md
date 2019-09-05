# 复选框的ajax提交

## AJAX向后台传输数据

### 一、多个checkbox使用AJAX向后台传输数据的简单方式

1、获取checkbox的所有已经选择的值

```js
var arr = new Array();

$("input[type='checkbox']:checked").each(function (index, item) {
	arr.push($(this).val());
});
```

2、向后台传输数据时需要对数据序列化

```js
data : {selectid : JSON.stringify(arr)},
```

3、后台接收的方式

```java
HttpServletRequest request = ServletActionContext.getRequest();
String selectidArr = request.getParameter("selectid");
String[] attr = selectidArr.split(",");
for(String s:attr) {
	int i =Integer.parseInt(s);
	TypeService.delType(i);
}
```

参考：

<https://blog.csdn.net/qq_25264951/article/details/76975303>

<https://blog.csdn.net/qq_39514287/article/details/78049466>

<https://blog.csdn.net/sinat_36553913/article/details/78418098>

<https://blog.csdn.net/qq_37796017/article/details/86490292>
