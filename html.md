### doctype的作用
>  <!DOCTYPE>声明必须位于文档的第一行，位于<html>标签前面
>  <!DOCTYPE>不是标签，是一种声明，他是告诉浏览器关于页面是以哪个HTML版本进行编写指令，在html4中<!DOCTYPE>引用DTD（文档类型定义），因为HTML4是基于SGML（标准通用标记语言），DTD规定了标记语言规则，这样浏览器才能正确的呈现内容。HTML5不基于SGML，所以不用引用DTD
>  该声明告诉浏览器以什么标准执行这个文档，声明不存在或者格式错误，就会导致文档以兼容模式呈现，标准模式的排版 和JS运作模式都是以该浏览器支持的最高标准运行。在兼容模式中，页面以宽松的向后兼容的方式显示,模拟老式浏览器的行为以防止站点无法工作。

###  总结一下获取数据类型的方法：

1.  typeof: 除了上面五种简单数据类型可以准确获取之外（null返回的是object），以及function返回的是function，其它的都返回的是object;
instanceof: 复杂数据类型如Array等都准确返回相应的boolean值，null只有对Object时返回true，然后对于基本数据类型则是返回false(只要是通过new运算符来进行初始化，
2. 然后通过instanceof来判断是否是某个类的实例，才会返回true，比如"var k = new Number(11); console.log(k instanceof Number)"，其返回true);
3. 使用constructor检测：对于上面的instanceof对于直接声明如：“var a = 1;”不能进行判断，我们可以通过使用constructor来实现判断，如“a.constructor==Number”(其返回true，不过对于“1.constructor==Number”这类直接用数值来访问constructor的情况是会报错的)，但对于null则仍然无法判断 ，而且会报错，比如“var k = null; console.log(k.constructor==Object)”；
4. 通过jquery$.type来获取数据类型，这里就不具体说明了。

###  position 各个属性
>  position:relative 
>   相对定位，原本位置会被保留，相对于自身原本位置进行偏移
>  position：absolute
>    绝对定位，脱离文档流，相对于最近一个拥有position的父级元素定位
>  position：fixed
>    固定定位，相对于浏览器窗口定位
>  position：static 默认布局
>  position：sticky粘性定位，它的行为就像 position:relative; 而当页面滚动超出目标区域时，它的表现就像 position:fixed;，它会固定在目标位置。
>  position：inherit 规定从父级元素继承position的值
###  border-box属性值和作用
1. box-sizing：content-box 宽度和高度分别应用到元素的内容框。在宽度和高度之外绘制元素的内边距和边框(元素默认效果)
2. box-sizing：border-box元素指定的任何内边距和边框都将在已设定的宽度和高度内进行绘制。
3. box-sizing：inherit规定元素是从父元素那里继承box-sizing的属性值