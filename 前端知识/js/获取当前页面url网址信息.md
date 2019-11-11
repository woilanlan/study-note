# 获取当前页面url网址信息

```log
参考：
https://www.jb51.net/article/82519.htm
https://www.cnblogs.com/7q4w1e/p/9549468.html
```

```js
//在当前页面执行登录
document.frmLogin.userid.value = "用户名";
document.frmLogin.pwd.value = "密码";
loginAccount(0);

//打开新窗口
var url = "https://www.baidu.com";
for(var i=0; i<2 ; i++){
openwin(url);
}
function openwin(url) {
var a = document.createElement("a");
a.setAttribute("href", url);
a.setAttribute("target", "_blank");
a.setAttribute("id", "camnpr");
document.body.appendChild(a);
a.click();
}
```
