# Classes

ES6 中的 classes 是簡化以原型繼承為基礎的物件導向設計模式

### 物件實字
```js
var o = {
    name: 'oo',
    showName: function(){
        console.log(this.name)
    }
}

o.showName();// oo
```

### 建構函式
```js
function O(){
    this.name = 'oo';
    this.showName = function(){
        console.log(this.name)
    }
}

var o = new O();
o.showName();
```
