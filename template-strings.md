# Template Strings

模版字串, 使用 ` ` ` 當定界符
```js
// 舊寫法
var temp = "<ul>\
    <li>name: {name}</li>\
    <li>phone: {phone}</li>\
    <li>email: {email}</li>\
</ul>";

var html = temp.
        replace(/\{name\}/, 'real name').
        replace(/\{phone\}/, 'real phone').
        replace(/\{email\}/, 'real email');
    
console.log(html)

// ES6
var name = 'real name',
    phone = 'real phone',
    email = 'real email',
    html = `
        <ul>
            <li>name: ${name}</li>
            <li>phone: ${phone}</li>
            <li>email: ${email}</li>
        </ul>
    `;

console.log(html)

```
