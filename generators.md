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

// 取得 Generator 實體物件,從1000開始
var o = uid(1000);

// for 循環 5 次
for (var i = 0; i < 5; i++) {
    console.log(o.next());
}
```

[迭代器介面]:iterators-for-of.md#interfaces