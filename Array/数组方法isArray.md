# Array

## 方法
### isArray

方法作用：用于确定传递的值是否是一个 Array。如果对象是 Array ，则返回true，否则为false。

是否改变原数组：否

返回值：boolean


以下都是`true`

```javascript
Array.isArray([]);
Array.isArray([1]);
Array.isArray(new Array());
Array.isArray(new Array('a', 'b', 'c', 'd'))
Array.isArray(Array.prototype); 
```

下面的函数调用都返回 false
```javascript
Array.isArray();
Array.isArray({});
Array.isArray(null);
Array.isArray(undefined);
Array.isArray(17);
Array.isArray('Array');
Array.isArray(true);
Array.isArray(false);
Array.isArray(new Uint8Array(32))
Array.isArray({ __proto__: Array.prototype });
```

环境如果没有isArray()

```javascript
if (!Array.isArray) {
  Array.isArray = function(arg) {
    return Object.prototype.toString.call(arg) === '[object Array]';
  };
}
```
