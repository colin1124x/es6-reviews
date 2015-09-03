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
console.log(o.hasOwnProperty('name')); // true
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
console.log(o.hasOwnProperty('name')); // true

```

### 建構函式 + 原型擴充
```js

function O(){}
O.prototype = {
    name: 'oo',
    showName: function(){
        console.log(this.name)
    }
};

var o = new O();
o.showName();
console.log(o.hasOwnProperty('name')); // false
console.log(o._constructor.prototype.hasOwnProperty('name')); // true
```

### ES6 Classes

實做建構函式
```js

class O {
    constructor(){
        this.name = 'oo';
        this.showName = function(){
            console.log(this.name)
        }
    }
}

var o = new O();
o.showName();
console.log(o.hasOwnProperty('name')); // true

```

實作建構函式 + 原形擴充

```js
class O {
    constructor(){

    }
    get name() {
        return 'oo';
    }
    showName(){
        console.log(this.name)
    }
}

var o = new O();
o.showName();
console.log(o.hasOwnProperty('name')); // false

```

