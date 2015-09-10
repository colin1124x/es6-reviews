# Generators

Generators 簡化迭代循環的動作流程<br>
此處關鍵是 `function*` 與 `yield` 兩個關鍵詞搭配運用

- 使用 `function*` 宣告的函式將會返回一個 Generator 實體(實做[迭代器介面])
- 內部使用 `yield` 將值傳出


### 簡單範例
```js
function* uid(n){
    while (true) yield n++;
}

// 取得 Generator 實體物件,從1001開始
var o = uid(1001);

// for 循環 5 次
for (var i = 0; i < 5; i++) {
    console.log(o.next());
}

var ret;
while ((ret = o.next()) && ret.value <= 1010) {
    console.log(ret)
}
```

### 應用
```js
var Num = function(){
    var renew = function*(){var n = 1;while (true) yield n++;},
        g = renew(),
        me = this;
    
    this.take = function(n){
        var ret = [];

        while (n-- > 0) {
            ret.push(g.next().value)
        }
        
        g = renew();
        
        return ret;
    };
    
    // 過濾器
    this.filter = function(filter){
        if (typeof filter == 'function') {
            var _g = g;
            g = (function*(){
                while (true) {
                    var v = _g.next().value;
                    if (filter(v)) yield v;
                }
            })();
        }
        return me;
    };
    
    // 過濾 奇數
    this.isOdd = function(){
        return me.filter(function(n){return n % 2;});
    };
    
    // 過濾 偶數
    this.isEven = function(){
        return me.filter(function(n){return n % 2 == 0;});
    };
}

var num = new Num();

console.log(num.filter(function(n){return n % 2 == 0;}).take(5)); // [2,4,6,8,10]
console.log(num.isOdd().take(10));

```

[迭代器介面]:iterators-for-of.md#interfaces