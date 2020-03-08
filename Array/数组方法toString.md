# Array

## 方法
### toString

作用:返回一个字符串，表示指定的数组及其元素

返回值：字符串

```javascript
let a = [1,2,3]
a.toString(); // "1,2,3"
```

> 当数组里面有null,undefined时 会被转换成空

```javascript
let a = [1,null,3]
a.toString(); // "1,,3"


let b = [1,undefined,3]
b.toString(); // "1,,3"
```