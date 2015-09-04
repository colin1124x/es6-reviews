# Destructuring

解構賦值

```js
function getSomeData(url) {
    if (url) {
        return [{data: 123}, null];
    }
    
    return [null, new Error];
    
}

// 情境: 容錯處理
// 仿 go 的風格
var [ret, err] = getSomeData();

console.log(ret, err)

```
