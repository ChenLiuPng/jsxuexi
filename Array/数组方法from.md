# Array

## 方法
### from

`Array.from()`方法从一个类似数组或者可迭代对象创建一个新的，浅拷贝的数组实例。

#### 参数

+ 第一个参数 想要转换成数组的伪数组对象或可迭代对象

```javascript
// 当传入Number boolean 会返回一个空数组
Array.from(1); // []

Array.from(true); // []

// 当传入String类型 会返回以单个字符形成的数组
// 从 String 生成数组
Array.from("1"); // ["1"]

Array.from('tail'); // ['t','a','i','l']

Array.from([1,2,3]); // [1,2,3];


// 返回跟传入类数组或可迭代对象一样的新数组

//从 Set 生成数组
Array.from(new Set(['A', 'B', 'C'])); // ["A", "B", "C"]

// 从 Map 生成数组
let c = new Map([[1, 'x'], [2, 'y'], [3, 'z']]);
Array.from(c); // [[1, 'x'], [2, 'y'], [3, 'z']]
Array.from(c.values()); // ['x','y','z']
Array.from(c.keys()); // [1, 2, 3]

// 从类数组对象（arguments）生成数组
function fn(){
    return Array.from(arguments);
}
fn(1,2,3); // [1,2,3]


```

+ 第二个参数 新数组中的每个元素会执行该回调函数 ,(value,index)

> 第一个参数是值，第二个参数是下标

```javascript
Array.from([1, 2, 3], v => v + v);// [2,4,6]
Array.from([1, 2, 3], (v,i) => i);// [0,1,2]
```
> 特殊用法，可以利用类数组对象（包含length属性）和下标来创建一个数组

```javascript
Array.from({length:5}, (v,i) => i); // [0,1,2,3,4]
```

> range
```javascript

const range = (start,stop,step) => Array.from({length:(stop-start)/step+1},(_,i)=>start+(i*step))

range(0,1,1); // [0,1]

range(0,9,2); // [0, 2, 4, 6, 8]

range('A'.charCodeAt(0), 'Z'.charCodeAt(0), 1).map(x => String.fromCharCode(x));
// ["A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U", "V", "W", "X", "Y", "Z"]
```

> 数组去重合并
```javascript
function combine(){ 
    let arr = [].concat.apply([], arguments);  //没有去重复的新数组 
    return Array.from(new Set(arr));
} 

var m = [1, 2, 2], n = [2,3,3]; 
console.log(combine(m,n)); // [1,2,3]
```

> 第三个参数 改变map的this指向

```javascript
let diObj = {
  handle: function(n){
    return n + 2
  }
}
Array.from([1, 2, 3, 4, 5],function(x){return this.handle(x)},diObj)
```

`from()的length` 返回新数组的长度
```javascript
Array.from('tail').length; // 4
```