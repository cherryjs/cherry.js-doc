duoshuo: 1001
title: 主页
url: /

## Cherry.js

Cherry.js 是一个基于原型扩展的 JavaScript 工具库，同时支持在浏览器端和 Node 环境中使用。

### 在浏览器中使用 cherry.js

只要引入一个js文件：

    <script src="cherry.min.js"></script>

接下来，享受 cherry.js 吧～

    $C(function(){
        var arr = ['a','b','c','d'];
        arr.$swap(0,2);
        console.log(arr); //return ['c','b','a','d'];

        var obj_1 = { a:{b:1}, c:[1,2,3] };
        var obj_2 = { a:{b:1}, c:[1,2,3] };
        console.log( obj_1 === obj_2 );     //return false;
        console.log( obj_1.$equal(obj_2) );  //return true;
    });

`$C`是在 cherry.js 中使用的唯一一个全局变量。像`$C(function(){...})`这样的语句块你一定不会陌生，这里我们称之为 Cherry 语句块。在 Cherry 语句块中，你可以尽情使用 cherry.js 所提供的库函数，而在 Cherry 语句块外，那些库函数就消失地无影无踪了。

Cherry.js 中库函数一般的命名规则是：**`XXX.prototype.$xxx`**。所以你所使用的其他库如果不会与这样的写法冲突的话，比较推荐以下写法： 

    $C.bind();
    /*
     * do anything you want with cherry.js
     */
    
    //And ... when you don't want to use cherry any more, you can call `$C.unbind()`
    $C.unbind();

### 浏览器支持

- Firefox(Gecko): 4.0+
- Chrome: 5+
- Internet Explorer: 9+
- Safari: 5+
- Opera: 11.60+

### 在Node中使用 cherry.js 

cherry.js 同样支持在 Node 环境中使用。

#### 使用 npm 安装

    npm install --save-dev cherry.js

#### 声明$C

    var $C = require('cherry.js');

    $C(function(){
        var arr = ['a','b','c','d'];
        arr.$swap(0,2);
        console.log(arr); //return ['c','b','a','d'];
    });