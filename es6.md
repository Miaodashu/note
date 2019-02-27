## ES6 

### let const
新增了let 和 const 关键字，用来声明变量，识别块级作用域；只能声明之后才能使用，否则会报错；
使用let命令声明变量之前，该变量都是不可用的。
const用来声明常量
### 字符串
1. for of 循环可以用来遍历数组，字符串，
       var arr= [1,2,3,4,5];
        var str = 'abcd'
        for(const item of arr){
            console.log(item)//1,2,3,4,5
         }
        如果是str则输出的是a,b,c,d
2. 新增includes(), startsWith(), endsWith() 
    以前只有`indexOf`方法来判断一个字符串里面是否另外的字符串；
    includes()：返回布尔值，表示是否找到了参数字符串。
    startsWith()：返回布尔值，表示参数字符串是否在原字符串的头部。
    endsWith()：返回布尔值，表示参数字符串是否在原字符串的尾部。
这三个方法都支持第二个参数，表示开始搜索的位置。
        let s = 'Hello world!';

        s.startsWith('Hello') // true
        s.endsWith('!') // true
        s.includes('o') // true
        
        s.startsWith('world', 6) // true
        s.endsWith('Hello', 5) // true
        s.includes('Hello', 6) // false
使用第二个参数n时，endsWith的行为与其他两个方法有所不同。它针对前n个字符，而其他两个方法针对从第n个位置直到字符串结束。
3. repeat()该方法返回一个字符串，表示将原字符串重复n次
        `'x'.repeat(3) // "xxx"
        'hello'.repeat(2) // "hellohello"
        'na'.repeat(0) // ""
`    参数如果是小数，会被取整。
     是负数或者Infinity，会报错。
     如果参数是 0 到-1 之间的小数，则等同于 0，这是因为会先进行取整运算。0 到-1 之间的小数，取整以后等于-0，repeat视同为 0。
     NaN等同于 0。
4. 函数的rest参数
5. 数组的展开运算符[...arr]

ES6 一共有 5 种方法可以遍历对象的属性。

（1）for...in

for...in循环遍历对象自身的和继承的可枚举属性（不含 Symbol 属性）。

（2）Object.keys(obj)

Object.keys返回一个数组，包括对象自身的（不含继承的）所有可枚举属性（不含 Symbol 属性）的键名。

（3）Object.getOwnPropertyNames(obj)

Object.getOwnPropertyNames返回一个数组，包含对象自身的所有属性（不含 Symbol 属性，但是包括不可枚举属性）的键名。

（4）Object.getOwnPropertySymbols(obj)

Object.getOwnPropertySymbols返回一个数组，包含对象自身的所有 Symbol 属性的键名。

（5）Reflect.ownKeys(obj)

Reflect.ownKeys返回一个数组，包含对象自身的所有键名，不管键名是 Symbol 或字符串，也不管是否可枚举。
