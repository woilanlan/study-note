# jquery常见问题

遇到问题，首先查询官方文档

## jquery

### 1、javascript中(function($){...})(jQuery)写法是什么意思

```log
这里实际上是匿名函数
function(arg){...}
这就定义了一个匿名函数，参数为arg

而调用函数 时，是在函数后面写上括号和实参的，由于操作符的优先级，函数本身也需要用括号，即：
(function(arg){...})(param)
这就相当于定义了一个参数为arg的匿名函数，并且将param作为参数来调用这个匿名函数

而(function($){...})(jQuery)则是一样的，之所以只在形参使用$，是为了不与其他库冲突，所以实参用jQuery

其实就等于
var fn = function($){....};
fn(jQuery);

简单理解是(function($){...})(jQuery)用来定义一些需要预先定义好的函数
$(function(){ })则是用来在DOM加载完成之后运行\执行那些预行定义好的函数
```

### 2、jquery中的$.fn的用法

参考：

- <https://www.cnblogs.com/qicao/p/8568158.html>
- <http://caibaojian.com/jquery-extend-and-jquery-fn-extend.html>
- <https://www.jb51.net/article/41903.htm>
- <https://blog.csdn.net/suyu_yuan/article/details/52690278>

### 3、Html页面获取项目路径

```js
window.onload=function(){
    getPath();
}

function getPath(){
    var pathName = document.location.pathname;
    var index = pathName.substr(1).indexOf("/");
    var result = pathName.substr(0,index+1);
    $("#path").val(result);
}
```

[纯html页面中js如何获得项目路径](https://www.cnblogs.com/youcong/p/9037961.html)

[Html之获取项目路径](https://blog.csdn.net/yelllowcong/article/details/78583350)

### 4、viewport的深入理解

[移动前端开发之viewport的深入理解](https://www.cnblogs.com/2050/p/3877280.html)

我们在开发移动设备的网站时，最常见的的一个动作就是把下面这个东西复制到我们的head标签中：

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=0">
```

该meta标签的作用是让当前viewport的宽度等于设备的宽度，同时不允许用户手动缩放。也许允不允许用户缩放不同的网站有不同的要求，但让viewport的宽度等于设备的宽度，这个应该是大家都想要的效果，如果你不这样的设定的话，那就会使用那个比屏幕宽的默认viewport，也就是说会出现横向滚动条。

这个name为viewport的meta标签到底有哪些东西呢，又都有什么作用呢？

meta viewport 标签首先是由苹果公司在其safari浏览器中引入的，目的就是解决移动设备的viewport问题。后来安卓以及各大浏览器厂商也都纷纷效仿，引入对meta viewport的支持，事实也证明这个东西还是非常有用的。

在苹果的规范中，meta viewport 有6个属性(暂且把content中的那些东西称为一个个属性和值)，如下：

属性 | 取值
--- | ---
width | 设置layout viewport  的宽度，为一个正整数，或字符串"width-device"
initial-scale | 设置页面的初始缩放值，为一个数字，可以带小数
minimum-scale | 允许用户的最小缩放值，为一个数字，可以带小数
maximum-scale | 允许用户的最大缩放值，为一个数字，可以带小数
height | 设置layout viewport  的高度，这个属性对我们并不重要，很少使用
user-scalable | 是否允许用户进行缩放，值为"no"或"yes", no 代表不允许，yes代表允许

这些属性可以同时使用，也可以单独使用或混合使用，多个属性同时使用时用逗号隔开就行了。

### 5、jQuery.extend()方法

jQuery.extend() 函数用于将一个或多个对象的内容合并到目标对象。

注意：

1. 如果只为$.extend()指定了一个参数，则意味着参数target被省略。此时，target就是jQuery对象本身。通过这种方式，我们可以为全局对象jQuery添加新的函数。
2. 如果多个对象具有相同的属性，则后者会覆盖前者的属性值。

```html
<div id="log"></div>
<script>
$(function () {
    var object1 = {
        apple: 0,
        banana: {weight: 52, price: 100},
        cherry: 97
    };
    var object2 = {
        banana: {price: 200},
        durian: 100
    };
    /* object2 合并到 object1 中 */
    $.extend(object1, object2);
    var printObj = typeof JSON != "undefined" ? JSON.stringify : function(obj) {
        var arr = [];
        $.each(obj, function(key, val) {
            var next = key + ": ";
            next += $.isPlainObject(val) ? printObj(val) : val;
            arr.push( next );
        });
        return "{ " +  arr.join(", ") + " }";
    };
    $("#log").append( printObj(object1) );
})
</script>
```

运行结果：

```log
{"apple":0,"banana":{"price":200},"cherry":97,"durian":100}
```
