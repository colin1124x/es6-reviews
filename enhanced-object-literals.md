# Enhanced Object Literals

物件實字擴充

```js
// 舊寫法 1
var o = {
    sayHello: function(){}
};

// ES6
var o = {
    sayHello(){}
};

// 舊寫法 2
function sayHello(){}
var o = {
    sayHello: sayHello
};

// ES6
function sayHello(){}
var o = {
    sayHello
};

```