# Template Strings

模版字串, 使用 ` ` ` 當定界符
```js
// 舊寫法
var temp = "<ul>\
    <li>name: {name}</li>\
    <li>phone: {phone}</li>\
    <li>email: {email}</li>\
</ul>";

document.getElementById('some-block').innerHTML = 
    temp.
    replase(/\{name\}/, 'real name').
    replase(/\{phone\}/, 'real phone').
    replase(/\{email\}/, 'real email');

```
