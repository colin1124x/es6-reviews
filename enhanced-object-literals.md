# Enhanced Object Literals

物件實字擴充

```js
// 舊寫法 1
var o = {
    sayHello: function(){}
};

// ES6
var o = {
    sayHello(){}
};

// 舊寫法 2
function sayHello(){}
var o = {
    sayHello: sayHello
};

// ES6
function sayHello(){}
var o = {
    sayHello
};

```

動態屬性
```js
// 共用
var uid = {
    _: 0,
    pull: function(){return this._++;}
};

// 舊寫法
var data = {};

data['x-'+uid.pull()] = 'some value...';
data['x-'+uid.pull()] = 'some value...';
data['x-'+uid.pull()] = 'some value...';
data['x-'+uid.pull()] = 'some value...';
data['x-'+uid.pull()] = 'some value...';
data['x-'+uid.pull()] = 'some value...';
data['x-'+uid.pull()] = 'some value...';
data['x-'+uid.pull()] = 'some value...';
data['x-'+uid.pull()] = 'some value...';
data['x-'+uid.pull()] = 'some value...';

console.log(data);

// ES6



var data = {
    ['x-'+uid.pull()]: 'some value...',
    ['x-'+uid.pull()]: 'some value...',
    ['x-'+uid.pull()]: 'some value...',
    ['x-'+uid.pull()]: 'some value...',
    ['x-'+uid.pull()]: 'some value...',
    ['x-'+uid.pull()]: 'some value...',
    ['x-'+uid.pull()]: 'some value...',
    ['x-'+uid.pull()]: 'some value...',
    ['x-'+uid.pull()]: 'some value...',
    ['x-'+uid.pull()]: 'some value...'
}

console.log(data);

```