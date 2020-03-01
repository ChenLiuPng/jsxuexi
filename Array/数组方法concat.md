# Array

## 方法
### concat

方法作用：用于合并两个或多个数组。

是否改变原数组：否

返回值：新数组

```javascript
const a1 = ['a','b','c'];
const a2 = ['d','e','f'];
const a3 = a1.concat(a2);


console.log(a1); // ['a','b','c']
console.log(a2); // ['d','e','f']
console.log(a3); // ['a','b','c','d','e','f'];


// const a1 = ['a','b','c'];
// const a2 = ['d','e','f'];
// const a3 = a2.concat(a1);   // 按照谁先谁后排序

// console.log(a1); // ['a','b','c']
// console.log(a2); // ['d','e','f']
// console.log(a3); // ['a','b','c','d','e','f'];
// ["d", "e", "f", "a", "b", "c"]


```

+ 浅拷贝

```javascript
let a = [1,2,3]
let b = a.concat()
console.log(b);// [1, 2, 3]
b[0] = 2;
console.log(b); // [2, 2, 3]
console.log(a); // [1, 2, 3]
```

+ 参数是对象引用类型 改变原对象的参数 会改变新数组里面对象的值

```javascript
let a = [1,2,3]
let b = {name:'tail'};
let c = a.concat(b)
console.log(c); // [1,2,3,{name:'tail'}];
b.name = 'tail1';
console.log(c); // [1,2,3,{name:'tail1'}];
```
+ 参数是基本数据类型 改变原对象的参数 不会改变新数组里面的值

```javascript
let a = [1,2,3]
let b = 1;
let c = a.concat(b)
console.log(c); // [1,2,3,1];
b = 2;
console.log(c); // [1,2,3,1];
```