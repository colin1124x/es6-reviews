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

動態屬性
```js
// 舊寫法
var data = {};
// 這邊用上 jQuery 來簡化 dom select 的複雜度
// 情境: 從 form 內的 input 建立 ajax 需要的傳遞資料 
$('form input[name]').each(function(){
    data[this.name.toLowerCase()] = encodeURI(this.value);
});

```