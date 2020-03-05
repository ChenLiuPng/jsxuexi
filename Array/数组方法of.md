# Array

## 方法
### of

作用：创建一个具有可变数量参数的新数组实例，而不考虑参数的数量或类型

返回值: 新数组

```javascript
let a = Array.of(7); // [7]
let b = Array.of(1, 2, 3); // [1,2,3]
Array.of(undefined); // [undefined]
```


兼容性:
```javascript

if (!Array.of) {
  Array.of = function() {
    return Array.prototype.slice.call(arguments);
  };
}

```