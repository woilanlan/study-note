# JS合并两个数组的方法

[JS合并两个数组的方法](https://www.cnblogs.com/koala0521/p/7278056.html)

1、concat

js的Array对象提供了一个叫concat()方法，连接两个或更多的数组，并返回结果。

var c = a.concat(b);//c=[1,2,3,4,5,6];

这里有一个问题，concat方法连接a、b两个数组后，a、b两个数组的数据不变，同时会返回一个新的数组。这样当我们需要进行多次的数组合并时，会造成很大的内存浪费，所以这个方法肯定不是最好的。

2、apply

函数的apply方法有一个特性，那就是func.apply(obj,argv)，argv是一个数组。所以我们可以利用这点，直接上代码：

a.push.apply(a,b);

[js中数组的合并和对象的合并](https://www.cnblogs.com/xingxiangyi/p/6416468.html)
