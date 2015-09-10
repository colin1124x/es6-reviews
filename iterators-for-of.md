# Iterators + For .. Of

迭代器

```js
// 傳統迭代做法

var arr = ['a', 'b', 'c', 'd'];

for (var i = 0, len = arr.length; i < len; i++) {
    console.log(arr[i]);
}

// 缺點:
// 1. 每次要迭代該陣列都需要控制三個值 - 起點值,終點值,累加值
// 2. 在js scope 實做下暴露出過多程序不須關心的拋棄式變數
```

```js
// 傳統進階做法
function each(arr, callback) {
    callback = typeof callback == 'function' ? callback : function(){};
    for (var i = 0, len = arr.length; i < len; i++) {
        callback.call(arr[i], arr[i], i);
        //callback(arr[i], i); // ES5 行為
    }
}

each(['a', 'b', 'c', 'd'], function(v, i){
    console.log(this, ''+this, v, i);
});
```

```js
// ES5
['a', 'b', 'c', 'd'].forEach(function(v, i){
    console.log(v, i);
});
```