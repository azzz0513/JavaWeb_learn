JavaScript是一种解释性的脚本语言。不同于C、C++、Java等语言先编译后执行，JavaScript不会产生编译出来的字节码文件，而是在程序的运行过程中对源文件逐行进行解释
JavaScript是一种基于对象的脚本语言，它不仅可以创建对象，也能使用现有的对象。但是面向对象的三大特性：封装、继承、多态中，JavaScript能够实现封装，可以模拟继承，但是不支持多态，所以它不是一门面向对象的语言
JavaScript中也有明确的数据类型，但是声明一个变量后它可以接收任何类型的数据，并且会在程序执行过程中根据上下文自动转换类型
JavaScript是一种采用事件驱动的脚本语言，它不需要经过Web服务器就可以对用户的输入做出响应
JavaScript脚本语言不依赖于操作系统，仅需要浏览器的支持。因此一个JavaScript脚本在编写后可以带到任意机器上使用，前提是机器上的浏览器支持JavaScript语言


##### JS的引入方式
==注意==：
- 一个html中可以有多个script标签
- 一对script标签不能仅在引入外部js文件又定义内部js脚本
- script标签如果用于引入外部js文件，中间最好不要有任何字符，包括空格和换行

###### 内部脚本方式引入
在head中通过一对script标签定义脚本代码
代码：
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .btn1 {
            width: 150px;
            height: 40px;
            font-size: 24px;
            font-family: '隶书';
            background-color: aqua;
            color: royalblue;
            border: 3px solid blue;
            border-radius: 5px;
        }
    </style>
    <script>
        // 通过function 函数名() {} 的方式定义函数
        function surprise() {
            // 弹窗提示
            alert('惊喜');
        }
    </script>
</head>
<body>
    <!--调用函数需要带括号()-->
    <button class="btn1" onclick="surprise()">点我有惊喜</button>
</body>
```
效果：
点击按钮后
![alt text](image-31.png)

###### 外部脚本文件引入
在head中通过一对script标签引入外部js文件
代码：
```js
function surprise() {
    // 弹窗提示
    alert('惊喜');
}
```
```html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .btn1 {
            width: 150px;
            height: 40px;
            font-size: 24px;
            font-family: '隶书';
            background-color: aqua;
            color: royalblue;
            border: 3px solid blue;
            border-radius: 5px;
        }
    </style>
    <script src="js/button.js" type="text/javascript"></script>
</head>
<body>
    <button class="btn1" onclick="surprise()">点我有惊喜</button>
</body>
```
效果与前面一致


##### JS的数据类型和运算符
###### 数据类型
- 数值类型：数值类型统一为number，不区分整数和浮点数
- 字符串类型：字符串类型为string和Java中的String相似，JS中不严格区分单双引号，都可以用于表示字符串
- 布尔类型：布尔类型为boolean和Java中的boolean相似，但是在JS的if语句，非空字符串会转换为'真'，非零数字也会认为是'真'
- 引用数据类型：引用数据类型对象是Object类型，各种对象和数组在JS中都是Object类型
- function类型：JS中的各种函数属于function数据类型
- 命名未赋值：js为弱类型语言，统一使用var声明对象和变量，在赋值时，才确定真正的数据类型，变量如果只声明没有赋值的话，数据类型为undefined