duoshuo: 1004
title: 详述cherry.js
url: /detail

## Cherry.js

Cherry.js是一个扩展了内置对象prototype的工具库。但它不同于Prototype.js，它仅仅在JavaScript本身的语言层面上进行扩展，而并不去关心JavaScript以外的东西，比如DOM。

### Cherry.js的定位与优势

其实在定位上，Cherry.js和underscore想要完成的事情一样，只是去完成了一些“本该放在JavaScript标准中的”常用函数。和其运行环境无关。不管是在前端还是后端（iOS的开发现在也支持使用javascript了），都可以使用Cherry.js或者underscore这样的工具库。那么相比于underscore，Cherry.js的优势是什么呢？

简单点来说：**Cherry.js可以最大限度地发挥JavaScript原型链的理念。**

拿最容易理解的方法`$equal`来举个例子，Cherry.js提供了针对Object, String, Array, Number, Boolean, Date, RegExp等内置对象的$equal函数。
```
var obj_1 = { a:{b:1}, c:[1,2,3] };
var obj_2 = { a:{b:1}, c:[1,2,3] };
console.log( obj_1 === obj_2 );     /* return false; */
console.log( obj_1.$equal(obj_2) );  /* return true; */
```

用户可以自定义自己的`$equal`方法。通过JS的原型链，`$equal`方法显得尤其出色：

```
var Person = function(name, age) {
    this.name = name;
    this.age = age
}

Person.prototype.$equal = function(p2) {
    return this.name === p2.name;
}

var obj1 = {
    person: new Person('Bob', 15)
};

var obj2 = {
    person: new Person('Bob', 19)
};

console.log( obj1.$equal(obj2) );
```

### Cherry.js如何解决扩展内置对象prototype的一般问题

关于该问题最初的讨论来自于 [知乎 | 为什么不要直接在Object.prototype上定义方法？](http://www.zhihu.com/question/26924011)

#### 问题1: 代码可能向上不兼容

如果目前Cherry.js实现的方法未来与ECMAScript新标准中涵盖的方法重名了，那原来写的代码可能就向上不兼容了。举个例子会比较直观，假设Cherry.js实现了一个`String.prototype.at`方法，然后用户在自己的代码中使用了这个方法。ECMAScript 7却也实现有那么一个`String.prototype.at`方法，这样不就会覆盖ES标准本身的实现了吗？如果这些方法还是`writable: false`的，还会报错！

**Cherry.js的解决手段是：给所有的方法加上`$`前缀**。可以看到所有的Cherry.js方法都有这么一个前缀。ES标准一般不会使用这样的命名方法，所以这样就可以大胆放心地使用Cherry.js啦！

#### 问题2: 出了Bug不太好定位问题

我们一直在致力于完善Cherry.js的文档，以及错误处理机制。