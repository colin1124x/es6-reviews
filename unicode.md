# Unicode

相容支援完整的 unicode<br>

```js
// ES5.1 2字節中文字
"𐮷".length == 2
```

### 正規表達式多了 `u` 旗標
```js
// 等義於下列編碼區段
/(?:[\0-\t\x0B\f\x0E-\u2027\u202A-\uD7FF\uE000-\uFFFF]|[\uD800-\uDBFF][\uDC00-\uDFFF]|[\uD800-\uDBFF](?![\uDC00-\uDFFF])|(?:[^\uD800-\uDBFF]|^)[\uDC00-\uDFFF])/
```

