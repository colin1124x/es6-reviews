# Default + Rest + Spread

預設值
```js
// origin
function greet(target)
{
    target = typeof target == 'undefined' ?  'world' : target;
    console.log('Hello', target);
}

// ES6
function greet(target = 'world')
{
    console.log('Hello', target);
}

greet(); // Hello world
greet('John');

```

Rest
```js
// origin
function merge(base) {
    // 主要差別在省掉這行處理
    var others = Array.prototype.slice.call(arguments, 1),
        tmp = [];
    others.forEach(function(arr){
        tmp = tmp.concat(arr);
    });
    
    return base.concat(tmp);
}

// ES6
function merge(base, ...others) {
    var tmp = [];
    others.forEach(function(arr){
        tmp = tmp.concat(arr);
    });
    
    return base.concat(tmp);
}

// test
var b = ['a', 'b'];
console.log(merge(b, ['c'], ['d']), b)
```

Spread
```js
// 共用
function sum(a, b, c) {
    return a + b + c;
}

// origin
var total = sum.apply(null, [1, 2, 3]);

// ES6
var total = sum(...[1, 2, 3])

```