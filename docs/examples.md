## Array
### Array.$swap(index1, index2)
`Array.$swap(index1, index2)` will exchange the positions of these two elements.

    $C(function(){
      var arr = [1,2,3];
      arr.$swap(0,2);
      console.log(arr);  //[3,2,1];
    });

### Array.$intersect(arr)
`Array.$intersect(arr)` return an intersection array with [arr].

    $C(function(){
      var arr = [1, 2, 3];
      arr.$intersect([3, 2, 4]); //[2, 3]
    });

### Array.$unite(arr)
`Array.$intersect(arr)` return an union array with [arr].

    $C(function(){
      var arr = [1, 2, 3];
      arr.$unite([2, 4, 1]); //[1, 2, 3, 4]
    });

## Object
### Object.$clone()
`Object.$clone()` will create a duplicate of the caller.

    $C(function(){
      var a = {b:1};
      var x = a.$clone(); // <x> is a duplicate of <a>
      x.b = 2;
      console.log(a.b);  //return 1; because the change on <x> will not affect <a>.
    });

### Object.$equal(obj)
`Object.$equal(obj)` will show you if [this] is equal to [obj] when **Only** considering the value.
    
    $C(function(){
      var obj_1 = { a:{b:1}, c:[1,2,3] };
      var obj_2 = { a:{b:1}, c:[1,2,3] };
      console.log( obj_1===obj_2 );       //return false;
      console.log( obj_1.$equal(obj_2) );  //return true;
    });

### Object.$debug(message)
`Object.$debug(message)` make it more easily to debug when developing.

    $C(function(){
      var t = 100;
      //...
      t.$debug("t...");  //console print: Debug Message: t..., Value: 100
    });

## String

### String.$trim()
`String.$trim()` will remove the spaces at the beginning and end.

    $C(function(){
        var str = "     hello world    ";
        console.log(str.trim()); //"hello world"
    })

### String.$removeSpace()
`String.$removeSpace()` will remove the spaces between the words.

    $C(function(){
        var str = "hello world ! ! !";
        console.log(str.$removeSpace()); //"helloworld!!!"
    })