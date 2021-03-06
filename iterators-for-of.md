# Iterators + For .. Of

迭代器模式
### interfaces
```js
// next 方法回傳結構體
interface IteratorResult {
  done: boolean;
  value: any;
}
// 迭代器必須實做此方法
interface Iterator {
  next(): IteratorResult;
}

// for .. of 進入點,利用此方法取得迭代器物件
interface Iterable {
  [Symbol.iterator](): Iterator
}
```


### 傳統迭代做法
```js
var arr = ['a', 'b', 'c', 'd'];

for (var i = 0, len = arr.length; i < len; i++) {
    console.log(arr[i]);
}

// 缺點:
// 1. 每次要迭代該陣列都需要控制三個值 - 起點值,終點值,累加值
// 2. 在js scope 實做下暴露出過多程序不須關心的拋棄式變數
```

### 傳統進階做法
```js
function each(arr, callback) {
    
    if (typeof callback != 'function') return;
    
    for (var i = 0, len = arr.length; i < len; i++) {
        callback.call(arr, arr[i], i);
        //callback(arr[i], i); // ES5 行為
    }
}

each(['a', 'b', 'c', 'd'], function(v, i){
    console.log(this, ''+this, v, i);
});
```
### ES5
```js
// ES5
['a', 'b', 'c', 'd'].forEach(function(v, i){
    console.log(v, i);
});
```

### 瀏覽器不支援 forEach 時,原型擴充方法(不建議使用)
```js
Array.prototype.myForEach = function(callback){
  if (typeof callback == 'function') {
    for (var i = 0, len = this.length; i < len; i++) {
      callback.call(this, this[i], i)
    }
  }

  return this;
};

['a', 'b', 'c', 'd'].myForEach(function(v, i){
  console.log(this, v, i)
});

```

### ES6
```js
var MyIterator = function(arr){
    return {
        // 此方法是迭代模式溝通關鍵
        // for .. of 的進入點, 為了取得 {next: {done: bool, value: ? }}
        [Symbol.iterator](){
            // 使用舊語法,以減少干擾
            var current = 0,
                len = arr.length;

            return {
                next: function(){
                    return { done: current >= len, value: arr[current++]};
                }
            }
        }
    }
}

var arr = MyIterator(['a', 'b', 'c', 'd']);

for (var i of arr) {
    console.log(i);
}

```

迭代模式是建立在 duck-typed interfaces (鴨式定型) 的基礎上.<br>
簡單說 "叫聲像鴨子,走起路來像鴨子,那就可以把它當鴨子"