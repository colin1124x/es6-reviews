# Arrows

` => ` 是 javascript 中的 function 縮寫

 > 依照說明範例,有些微的差異. <br>
 > 主要在匿名函式作用域內的 this 關鍵字參照到的實體不同
 
舉例
```js
// 舊寫法
function Car() {
    
    var me = this;
    
    this.speed = 0;
    
    setInterval(function(){
        // 此處必須使用 me 來參照到建構式實體物件
        me.speed += 1;
    }, 1000);
    
}
```

```js
// ES6 Arrows 寫法
function Car() {
    this.speed = 0;
    
    // 註: 儘管在ES6模式下仍必須使用 Arrows 宣告匿名函式才有此特性
    setInterval(() => { this.speed++ }, 1000);
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
// 自動回傳最後的演算值
function (n) { return n + 1; }
```

#### 多行

```js
n => {n + 1}
```
等同於
```js
// 沒有回傳,必須自行宣告
function (n) { n + 1; }
```