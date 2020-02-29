# Array

## 属性
### length
`length` 返回或设置一个数组的元素个数 
+ 特性：0-2的32次方-1

 如果数组的长度大于4294967295或者小于0，那么将抛出 `RangError：Invalid array length`

+ 总是大于数组最高项的下标
 
```javascript
let a = ['tail','tail1']; // 0:'tail',1:'tail1' 最高项下标：1
a.length; // 数组长度：2
// 2>1

```
> 可以通过`array.length-1` 来获取最高项下标

```javascript
let a = ['tail','tail1'];
a.length-1; // 1
```
> 可以通过`array[array.length-1]` 来获取最高项的值

```javascript
let a = ['tail','tail1'];
a[a.length-1]; // tail1
```
> 使用比数组最高项下标的下标给数组赋值，会默认增加length的长度

```javascript
let a = ['tail','tail1'];
a[2] = 'tail2';
a.length;  // 3
```

+ 扩展数组 

```javascript
let a = [];
a.length = 3;
console.log(a) // [empty,empty,empty]
a[0]; // undefined
a[1]; // undefined
a[2]; // undefined
typeof a[0] === 'undefined'; // true
```

+ 截断数组 

```javascript
let a = [1,2,3];
a.length = 2;
console.log(a); // [1,2]
```
