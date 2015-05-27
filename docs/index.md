duoshuo: 1001
title: 主页
url: /

## Cherry.js

Cherry.js 是一个基于原型扩展的 JavaScript 工具库，同时支持在浏览器端和 Node 环境中使用。

### 在浏览器中使用 cherry.js

只要引入一个js文件：

    <script src="cherry.min.js"></script>

接下来，享受 cherry.js 吧～

    var arr = ['a','b','c','d'];
    arr.$swap(0,2);
    console.log(arr); //return ['c','b','a','d'];

    var obj_1 = { a:{b:1}, c:[1,2,3] };
    var obj_2 = { a:{b:1}, c:[1,2,3] };
    console.log( obj_1 === obj_2 );     //return false;
    console.log( obj_1.$equal(obj_2) );  //return true;

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

    require('cherry.js');

    var arr = ['a','b','c','d'];
    arr.$swap(0,2);
    console.log(arr); //return ['c','b','a','d'];
    