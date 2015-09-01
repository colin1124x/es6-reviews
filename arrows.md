# Arrows

` => ` 是 javascript 中的 function 縮寫

 > 依照 MDN 的說明範例,有些微的差異. <br>
 > 主要在匿名函式作用域內的this關鍵字參照到的實體不同
 
舉例
```js
// 建構函式
function Car() {
    
    var me = this;
    
    this.speed = 0;
    
    setInterval(function(){
        // 此處必須使用 me 來參照到建構式實體物件
        me.speed += 1;
    }, 1000);
    
}
```
 
### 多行與單行的差別

#### 單行
```js
n => n + 1;
```
等同於
```js
"use strict"
function (n) { return n + 1; }
```

#### 多行

```js
n => {n + 1}
```
等同於
```js
function (n) { n + 1; }
```