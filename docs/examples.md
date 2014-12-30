duoshuo: 1003
title: 简单的例子
url: /example

## Array
### Array.$swap(index1, index2)
接受两个数组索引作为参数，将this数组中对应的元素进行交换位置，返回值即这个数组本身。

    $C(function(){
      var arr = [1,2,3];
      arr.$swap(0,2);
      console.log(arr);  //[3,2,1];
    });

### Array.$intersect(arr)
接受一个数组参数，并返回它与这个数组的交集。

    $C(function(){
      var arr = [1, 2, 3];
      arr.$intersect([3, 2, 4]); //[2, 3]
    });

### Array.$unite(arr)
接受一个数组参数，并返回它与这个数组的并集。

    $C(function(){
      var arr = [1, 2, 3];
      arr.$unite([2, 4, 1]); //[1, 2, 3, 4]
    });

## Object
### Object.$clone()
将产生一个该对象的副本，并返回出来。

    $C(function(){
      var a = {b:1};
      var x = a.$clone(); // <x> is a duplicate of <a>
      x.b = 2;
      console.log(a.b);  //return 1; because the change on <x> will not affect <a>.
    });

### Object.$equal(obj)
将该对象与obj相比较，如果两者具有相同的属性，并且对应的属性值相同，那么该函数会返回true。
    
    $C(function(){
      var obj_1 = { a:{b:1}, c:[1,2,3] };
      var obj_2 = { a:{b:1}, c:[1,2,3] };
      console.log( obj_1===obj_2 );       //return false;
      console.log( obj_1.$equal(obj_2) );  //return true;
    });

### Object.$debug(message)
提供了一种使debug更顺畅的方法。

    $C(function(){
      var t = 100;
      //...
      t.$debug("t...");  //console print: Debug Message: t..., Value: 100
    });

## String

### String.$trim()
移除该字符串头尾的空字符。

    $C(function(){
        var str = "     hello world    ";
        console.log(str.trim()); //"hello world"
    })

### String.$removeSpace()
移除字符串中所有的空字符。

    $C(function(){
        var str = "hello world ! ! !";
        console.log(str.$removeSpace()); //"helloworld!!!"
    })