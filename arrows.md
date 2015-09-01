# Arrows

` => ` 是 javascript 中的 function 縮寫

 > 依照 MDN 的說明範例,有些微的差異. <br>
 > 主要在匿名函式作用域內的this關鍵字參照到的實體不同
 
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