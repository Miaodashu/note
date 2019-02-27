##typeof 和 instanceof 的区别
### typeof 
typeof方法返回的是一个字符串，表示数据类型。

数据类型 | Type
:-:|:-:|-:
Undefined | "undefined" 
Null|"object" 
布尔值|"boolean"
数值|"number"
字符串|"string"
Symbol|"symbol"
函数对象|"function"
任何其他对象|"object"
 

> 就是typeof来判断数据类型其实并不准确。比如数组、正则、日期、对象的typeof返回值都是object，这就会造成一些误差。

关于typeof的几个真题
1. > var y = 1, x = y = typeof x;
    x;

2. > 
    (function f(f){
    return typeof f();
    })(function(){ return 1; });

3. >  var foo = {
    bar: function() { return this.baz; },
    baz: 1
  };
  (function(){
    return typeof arguments[0]();
  })(foo.bar);

4. >   var foo = {
      bar: function(){ return this.baz; },
      baz: 1
    }
    typeof (f = foo.bar)();
5. >var f = (function f(){ return "1"; }, function g()  { return 2; })();
typeof f;
6. >  var x = 1;
  if (function f(){}) {
    x += typeof f;
  }
  x;
7. >  (function(foo){
    return typeof foo.bar;
  })({ foo: { bar: 1 } });

答案是"undefined","number","undefined","undefined","number","1undefined","undefined"


###instanceof运算符可以用来判断某个构造函数的prototype属性是否存在于另外一个要检测对象的原型链上。 原始数据就不能用这个方法，可以用Object.prototype.toString.call(str)这个方法来检测类型




参考于 [布瑞泽的童话][https://blog.csdn.net/mevicky/article/details/50353881](https://blog.csdn.net/mevicky/article/details/50353881)

###遍历数组和对象的方法
for in 用来遍历数组的话，遍历顺序有可能不是按照实际数组的内部顺序，使用for in会遍历数组所有的可枚举属性，包括原型。所以更适合遍历对象
for in 是遍历对象的键名  for of 是遍历的数组的值；
for of遍历的只是数组内的元素，而不包括数组的原型属性method和索引name
所以，遍历数组用for循环或者for of ，遍历对象是用for in

        var myArray=[1,2,4,5,6,7]
        for (var index of myArray) {
        console.log(index);// 1 2 4 5 6 7
        }

     Object.prototype.method=function(){
        console.log(this);
     }   
     var myObject={
            a:1,
            b:2,
            c:3
        }
        for (var key in myObject) {
        console.log(key);//a b c method
        }
>for in 可以遍历到myObject的原型方法method,如果不想遍历原型方法和属性的话，可以在循环内部判断一下,hasOwnPropery方法可以判断某属性是否是该对象的实例属性

    for (var key in myObject) {
        if（myObject.hasOwnProperty(key)){
            console.log(key);
        }
    }
> 可以通过ES5的Object.keys(myObject)获取对象的实例属性组成的数组，不包括原型方法和属性


