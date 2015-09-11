# Unicode

相容支援完整的 unicode<br>

```js
// ES5.1 2字節中文字
"𐮷".length == 2


"𐮷".charCodeAt(0).toString(16);
// d842, 第一字節的編碼轉16進位

"𐮷".charCodeAt(1).toString(16);
// dfb7, 第二字節的編碼轉16進位

"𐮷".codePointAt(0).toString(16);
// 20bb7

// 由上方導出 "𐮷"=="\ud842\udfB7"
"\u{20bb7}" == "\ud842\udfB7" // true

// * 編碼反推字符表

// 使用 fromCharCode
String.fromCharCode(0x20bb7); 
// 無法找到正確對應的編碼位置

// 使用 fromCodePoint
String.fromCodePoint(0x20bb7);
// 可正確找到字符

```

### 正規表達式多了 `u` 旗標
```js
// 等義於下列編碼區段
/(?:[\0-\t\x0B\f\x0E-\u2027\u202A-\uD7FF\uE000-\uFFFF]|[\uD800-\uDBFF][\uDC00-\uDFFF]|[\uD800-\uDBFF](?![\uDC00-\uDFFF])|(?:[^\uD800-\uDBFF]|^)[\uDC00-\uDFFF])/
```

