# Let + Const

控制變數作用域與不變性

```js
var x = 123;

{
    let x = 456;
    
    console.log('in block', x)
}

console.log('out block', x)


```