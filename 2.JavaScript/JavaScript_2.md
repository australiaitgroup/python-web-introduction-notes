# Class Notes

## Table of Contents

- [Class Notes](#class-notes)
  - [Resources](#resources)
  - [JavaScript_2](#javascript_2)
    - [if/else 结构](#ifelse-结构)
      - [score if-else 练习](#score-if-else-练习)
        - [solution 1: if/else](#solution-1-ifelse)
        - [solution 2: ternary operator (可以但不推荐)](#solution-2-ternary-operator-可以但不推荐)
    - [三元运算符 (分支少时可以用)](#三元运算符-分支少时可以用)
      - [判断成绩是否大于 90](#判断成绩是否大于-90)
      - [判断变量小于 10 时在前面添加 0](#判断变量小于-10-时在前面添加-0)
    - [switch 用法 (全等匹配)](#switch-用法-全等匹配)
      - [水果 switch 判断](#水果-switch-判断)
    - [循环](#循环)
      - [统计总分数和平均数](#统计总分数和平均数)
      - [计算 1-100 能被 3 整除的和](#计算-1-100-能被-3-整除的和)
      - [使用 while 计算 1-100 的和](#使用-while-计算-1-100-的和)
    - [console.log 设置 filter](#consolelog-设置-filter)
    - [Break 和 Continue](#break-和-continue)
      - [for 实现 break](#for-实现-break)
      - [forEach 实现 break](#foreach-实现-break)
      - [for 实现 continue](#for-实现-continue)
      - [forEach 实现 continue](#foreach-实现-continue)
      - [1-100 除了能被 7 整除的和](#1-100-除了能被-7-整除的和)
    - [Array](#array)
      - [求总和\&平均数](#求总和平均数)
      - [求数组最大值](#求数组最大值)
        - [solution 1: for 循环](#solution-1-for-循环)
        - [solution 2: Math.max()](#solution-2-mathmax)
      - [得到 array 的 index](#得到-array-的-index)
      - [array 转化成 string](#array-转化成-string)
    - [Object](#object)
      - [遍历 object 的 value](#遍历-object-的-value)
        - [solution 1](#solution-1)
        - [solution 2](#solution-2)

## Resources

[array_push](https://www.w3schools.com/jsref/jsref_push.asp)<br>
[array_pop](https://www.w3schools.com/python/ref_list_pop.asp)<br>
[array_unshift](https://www.w3schools.com/jsref/jsref_unshift.asp)<br>
[array_shift](https://www.w3schools.com/jsref/jsref_shift.asp)<br>

## JavaScript_2

<p align='center'><img src='../image/js.png' width='30%' height='30%' /></p>

### if/else 结构

```js
if (条件表达式) {
  执行语句1;
}
```

> 只有一条执行语句时, {}可以省略

#### score if-else 练习

##### solution 1: if/else

```js
let score = prompt("Please enter your score");
if (score >= 90) {
  console.log("A");
} else if (score >= 80) {
  console.log("B");
} else if (score >= 70) {
  console.log("C");
} else if (score >= 60) {
  console.log("D");
} else {
  console.log("E");
}
```

##### solution 2: ternary operator (可以但不推荐)

```js
let score = prompt("Please enter your score");
console.log(
  score >= 90
    ? "A"
    : score >= 80
    ? "B"
    : score >= 70
    ? "C"
    : score >= 60
    ? "D"
    : "E"
);
```

### 三元运算符 (分支少时可以用)

`syntax: 条件 ? 执行语句1 : 执行语句2`

#### 判断成绩是否大于 90

```js
let score = 85;
console.log(score > 90 ? "A" : "B"); // B
```

#### 判断变量小于 10 时在前面添加 0

```js
let num = prompt("Please enter  a number between 0~59");
let res = num < 10 ? "0" + num : num;
alert(res);
```

### switch 用法 (全等匹配)

> `多个case每个都要test下, case后面要记得加break`

`switch demo`

```js
const num = 3;
switch (num) {
  case 1:
    console.log(num);
    break;
  case 2:
    console.log(num);
    break;
  case 3:
    console.log(num);
    break;
  default:
    console.log("not match");
}
```

#### 水果 switch 判断

```js
let fruit = prompt("Please enter a fruit name: ");
switch (fruit) {
  case "apple":
    alert("$3/kg");
    break;
  case "banana":
    alert("$4/kg");
    break;
  default:
    alert(fruit + " is not available");
}
```

<hr>

### 循环

#### 循环目的

- 执行规律性的重复操作的需要

#### JS 中的主要循环

- for 循环
- while 循环
- do...while 循环

> 和 if/else 相似, 当循环体内部只有一条执行语句时, {}可以省略

```js
for (let i = 1; i <= 100; i++) {
  if (i === 1) {
    console.log("The person is 1 year old");
  } else if (i === 100) {
    console.log("The person is 100 years old");
  } else {
    console.log(i);
  }
}
```

#### 统计总分数和平均数

```js
let num = parseInt(prompt("total class number"));
let scoreSum = 0;
for (let i = 1; i <= num; i++) {
  let score = parseFloat(prompt(`请输入第${i}个学生的成绩`));
  scoreSum += score;
}
let average = scoreSum / num;
alert(`Total_score: ${scoreSum} \nAverage_score: ${average}`);
```

#### 计算 1-100 能被 3 整除的和

```js
let sum = 0;
for (let i = 1; i <= 100; i++) if (i % 3 === 0) sum += i;
console.log(sum); // 1683
```

#### 使用 while 计算 1-100 的和

```js
let sum = 0;
let i = 1;
while (i <= 100) {
  sum += i;
  i++;
}
console.log("sum", sum);
```

<hr>

### console.log 设置 filter

```js
console.log("featureA sum", 123);
console.log("feartureA average", 123);
```

> 之后在 filter 中输入"featureA", 就能有针对性地看到结果

<hr>

### Break 和 Continue

|       break        |               continue               |
| :----------------: | :----------------------------------: |
| **_退出整个循环_** | **_跳出本次循环<br>继续下一次循环_** |

_对于 array 来说, 需要用到 break 和 continue 时一般用 for 循环处理, 实际上 forEach 也能实现这一点, 但会有代价(如原 array 被清空). 除了上面的情况, 大多数情况使用 forEach 做遍历, 因为比较简洁_

#### for 实现 break

```js
const arr1 = [1, 2, 3, 4, 5];
for (let i = 0; i < arr1.length; i++) {
  if (arr1[i] === 3) break;
  console.log(arr1[i]); // 1 2
}

console.log(arr1); // [1, 2, 3, 4, 5]
```

#### forEach 实现 break

```js
const arr = [1, 2, 3, 4, 5];
arr.forEach((value) => {
  if (value === 2) arr.length = 0;
  console.log(value); // 1 2
});

console.log(arr); // []
```

#### for 实现 continue

```js
for (let i = 1; i <= 5; i++) {
  if (i === 3) continue;
  console.log(i); // 1 2 4 5
}
```

#### forEach 实现 continue

```js
[1, 2, 3, 4, 5].forEach((i) => {
  if (i === 3) return;
  console.log(i); // 1 2 4 5
});
```

#### 1-100 除了能被 7 整除的和

```js
let sum = 0;
for (let i = 1; i <= 100; i++) {
  if (i % 7 === 0) continue;
  sum += i;
}
console.log(sum); // 4315
```

<hr>

### Array

`array demo`

```js
let arr = new Array(); // 使用new Array()创建新数组
let arr1 = []; // 使用[]创建新数组
let arr2 = [1, 3, 5, 7];
console.log(arr2[0]); // 1
console.log(arr2[arr2.length - 1]); // 7
```

```html
<script>
  //用new创建数组 ['Ben',12] ['apple','orange','banana']
  let arr = new Array(); //创建一个空数组[]
  console.log("arr", arr);
  let arr1 = [];
  let arr2 = [1, 3, 5, 7];
  console.log(arr2.length); //数组长度4 index of last item == arr.length -1
  console.log(arr2[2]); //5 index从0开始
  console.log(arr[arr2.length - 1]); // last item value
  console.log(arr[10]); //没有这个元素时返回undefined
</script>
```

```html
<script>
  //修改length长度
  let arr = ["apple", "banana", "orange"];
  console.log("length", arr.length);
  arr[3] = "kiwi"; //add item
  console.log(arr);
  arr[1] = "grape";
  console.log(arr);
</script>
```

#### 求总和&平均数

```js
const arr = [2, 6, 1, 7, 4];
let sum = 0;
for (let i = 0; i < arr.length; i++) sum += arr[i];
const avg = sum / arr.length;
console.log(sum); // 20 console.log(avg); // 4
```

#### 求数组最大值

##### solution 1: for 循环

```js
const arr = [2, 6, 1, 77, 52, 25, 7];
let max = arr[0];
for (let i = 1; i < arr.length; i++) if (arr[i] > max) max = arr[i];
console.log(max);
```

##### solution 2: Math.max()

```js
const arr = [2, 6, 1, 77, 52, 25, 7];
console.log(Math.max(...arr));
```

`push方法`

- 改变原数组 (后面添加)
- 返回值是新数组 length

`pop方法`

- 改变原数组 (删除了最后一个元素)
- 返回的是最后面被删除的元素

`unshift方法`

- 改变原数组 (前面添加)
- 返回值是新数组 length

`shift方法`

- 改变原数组 (删除了开始的元素)
- 返回的是最前面被删除的元素

#### array 筛选

```html
<script>
  // 将数组 [2, 0, 6, 1, 77, 0, 52, 0, 25, 7] 中大于等于 10 的元素选出来，放入新数组。
  // 1、声明一个新的数组用于存放新数据newArr。
  // 2、遍历原来的旧数组， 找出大于等于 10 的元素。
  // 3、依次追加给新数组 newArr。
  // 方法1
  let arr = [2, 0, 6, 1, 77, 0, 52, 0, 25, 7];
  let newArr = [];
  let j = 0;
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] >= 10) {
      newArr[j] = arr[i];
      j++;
    }
  }
  console.log(newArr);
</script>
```

#### array 删除指定元素

```html
<script>
  //删除指定元素0
  // 将数组[2, 0, 6, 1, 77, 0, 52, 0, 25, 7]中的 0 去掉后，形成一个不包含 0 的新数组。
  // 1、需要一个新数组用于存放筛选之后的数据。
  // 2、遍历原来的数组， 把不是 0 的数据添加到新数组里面(此时要注意采用数组名 + 索引的格式接收数据)。
  // 3、新数组里面的个数， 用 length 不断累加。
  let arr = [2, 0, 6, 1, 77, 0, 52, 0, 25, 7];
  let newArr = [];
  let j = 0;
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] !== 0) {
      newArr[j] = arr[i];
      j++;
    }
  }
  console.log(newArr);
</script>
```

#### array 一些添加和删除元素的方法(都会改变原数组)

```html
<script>
  // 添加删除数组元素方法
  // 1. push() 在我们数组的末尾 添加一个或者多个数组元素   push  推
  let arr = [1, 2, 3];
  // arr[3] = 'hello'
  let result = arr.push("hello", "world");
  console.log("result", result);
  console.log(arr);
  //注意事项：
  // (1) push 是可以给数组追加新的元素
  // (2) push() 参数直接写 数组元素就可以了
  // (3) push完毕之后，返回的结果是 新数组的长度
  // (4) 原数组也会发生变化
  // 2. unshift 在我们数组的开头 添加一个或者多个数组元素

  // (1) unshift是可以给数组前面追加新的元素
  // (2) unshift() 参数直接写 数组元素就可以了
  // (3) unshift完毕之后，(重点1)返回的结果是 新数组的长度
  // (4) （重点2）原数组也会发生变化
  let arr2 = [1, 2, 3, 4, 5, "apple"];
  let result2 = arr2.unshift("banana", "kiwi");
  console.log("result2", result2);
  console.log("arr2", arr2);
  // 3. pop() 它可以删除数组的最后一个元素
  // (1) pop是可以删除数组的最后一个元素 记住一次只能删除一个元素
  // (2) pop() 没有参数
  // (3) pop完毕之后，返回的结果是 删除的那个元素
  // (4) 原数组也会发生变化
  let arr3 = [1, 2, 3, 4, 5];
  const result3 = arr3.pop();
  console.log("result3", result3); //5
  console.log("arr3", arr3); //[1,2,3,4]
  // 4. shift() 它可以删除数组的第一个元素

  // (1) shift是可以删除数组的第一个元素 记住一次只能删除一个元素
  // (2) shift() 没有参数
  // (3) shift完毕之后，返回的结果是 删除的那个元素
  // (4) 原数组也会发生变化
  let arr4 = [1, 2, 3];
  console.log(arr4.shift());
  console.log(arr4);
</script>
```

#### 得到 array 的 index

```js
let arr = ["red", "green", "blue", "pink", "blue"];
let index = arr.indexOf("blue");
console.log(index); // 2
let arr2 = ["red", "green", "blue", "pink", "blue"];
let index2 = arr2.lastIndexOf("blue");
console.log(index2); // 4
```

#### array 转化成 string

```js
let arr = ["red", "green", "blue", "pink", "blue"];
console.log(arr.toString()); // 'green,blue,red'
console.log(arr.join(" ")); // "green blue red"
```

> toString()和 join()不改变原数组

<hr>

### Object

`无序的集合`

> 对象 = 属性 + 方法

```js
var star = {
  name: "pink",
  age: 18,
  sex: "male",
  sayHi() {
    console.log("hello");
  },
};
console.log(star.name);
console.log(star["name"]);
star.sayHi();
```

#### 遍历 object 的 value

##### solution 1

```js
let obj = {
  name: "Chirs",
  age: 40,
  hobby: "codeing",
  gender: "female",
};
for (let key in obj) console.log(obj[key]);
```

##### solution 2

```js
let obj = {
  name: "Chirs",
  age: 40,
  hobby: "codeing",
  gender: "female",
};
for (let value of Object.values(obj)) console.log(value);
```
