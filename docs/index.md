Cherry.js is a JavaScript utility library, and it can run on both browser and Node. You can use javascript more easily with cherry.js. The sample follows:

## Use cherry.js in browser

Just include this script for using:

    <script src="cherry.min.js"></script>

And enjoy cherry.js:

    $C(function(){
        var arr = ['a','b','c','d'];
        arr.$swap(0,2);
        console.log(arr); //return ['c','b','a','d'];

        var obj_1 = { a:{b:1}, c:[1,2,3] };
        var obj_2 = { a:{b:1}, c:[1,2,3] };
        console.log( obj_1===obj_2 );     //return false;
        console.log( obj_1.$equal(obj_2) );  //return true;
    });

If you don't care about polluting the global namespace, you can:

    $C.bind();
    /*
     * do anything you want with cherry.js
     */

    //And when you don't want to use cherry any more, you can call $C('unbind')
    $C.unbind();

## Use cherry.js in Node.js

### Install

    npm install --save-dev cherry.js

### Use

    var $C = require('cherry.js');

    $C(function(){
        var arr = ['a','b','c','d'];
        arr.$swap(0,2);
        console.log(arr); //return ['c','b','a','d'];
    });