# Let + Const

控制變數作用域與不變性

```js
var x = 123;

{
    // let 將變數可視範圍限制在城市區塊內
    let x = 456;
    
    console.log('in block', x)
}

console.log('out block', x)
```

```js
const x = 123;

x = 456; // error
```