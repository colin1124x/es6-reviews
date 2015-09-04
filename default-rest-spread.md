# Default + Rest + Spread

預設值
```js
// origin
function greet(target = 'world')
{
    console.log('Hello', target);
}

// ES6
function greet(target)
{
    target = typeof target == 'undefined' ?  'world' : target;
    console.log('Hello', target);
}

greet(); // Hello world
greet('John');

```

rest
```

```
