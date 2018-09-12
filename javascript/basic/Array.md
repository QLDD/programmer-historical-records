## Array



##### 1、数组是对象的特殊形式



##### 2、创建

```js
let test = [];
```



##### 3、读写

```js
test[0] = 'hello world';
let str = test[0];
```



##### 4、属性

- length

``` js
let num = test.length;
let num = [].length;
```



##### 5、添加和删除

- 1、delete：删除指定元素的值，位置保留，值变为undefined

``` js
delete test[0];
```

- 2、push() 和 pop()   ==>   9、数组方法里面有介绍
- 3、unshift() 和 shift()   ==>   9、数组方法里面有介绍
- 4、splice()   ==>   9、数组方法里面有介绍



##### 6、遍历

- 1、for

``` js
let arrayTest = [1, 2, 3, 4, 5];
for (let i = 0; i < arrayTest.length; i++) {
    let value = arrayTest[i];
    //可以break
    //可以continue
}
```

- 2、for of

``` js
let arrayTest = [1, 2, 3, 4, 5];
for (let item of arrayTest) {
    let value = arrayTest[item];
    //可以break
    //可以continue
    //只读
}
```

- 3、foreach()   ==>   9、数组方法里面有介绍
- 4、map()   ==>   9、数组方法里面有介绍



##### 7、作为数组的字符串

``` js
let str = 'test';
str.charAt(0); // => 't'
str[1]; // => 'e'
```



##### 8、判断数组类型

- (ES5中) Array.isArray() 来判断未知的对象是否为数组

``` js
Array.isArray([]); // => true
Array.isArray({}); // => fasle
```



##### 9、数组方法

###### ES3

- 1、join()：将数组所有元素以分隔符的形式转化为字符串，不指定分隔符，默认为逗号

``` js
let arrayTest = [1, 2, 3];
arrayTest.join(); // => "1,2,3"
arrayTest.join(" "); // => "1 2 3"
arrayTest.join(""); // => "123"
let b = new Array(10);
b.join('-'); // => "---------" 9个
```

- 2、reverse()：逆序

``` js
let a = [1, 2, 3];
a.reverse(); // => a 是 [3, 2, 1]  a 本身改变
```

- 3、sort()：排序，在原数组上进行排序

``` js
//不带参数，按照字母表顺序排序
let a = ["banana", "cherry", "apple"];
a.sort(); // a 变为 ["apple", "banana", "cherry"]
let b = [33, 4, 1111, 222];
b.sort(); // b 变为 [1111, 222, 33, 4]
//带参数，参数必须是函数，该函数要比较两个值，然后返回一个用于说明这两个值的相对顺序的数字。
//比较函数具有两个参数 a 和 b
//若返回值小于0，a在前，b在后
//若返回值等于0，无所谓
//若返回值大于0，b在前，a在后
let c = [33, 4, 1111, 222];
c.sort((a, b) => {
    return a - b;
}); // c 变为 [4, 33, 222, 1111]
let d = [33, 4, 1111, 222];
d.sort((a, b) => {
    return b - a;
}); // d 变为 [1111, 222, 33, 4]
```

- 4、concat()：创建并返回一个新数组，新数组包括原来数组的元素和concat()的参数

``` js
let a = [1, 2, 3];
let b = a.concat(4, 5); // => [1, 2, 3, 4, 5]
let c = a.concat([4, 5]); // => [1, 2, 3, 4, 5]
let d = a.concat([4, 5], [6, 7]); // => [1, 2, 3, 4, 5, 6, 7]
let e = a.concat(4, [5, [6, 7]]); // => [1, 2, 3, 4, 5, [6, 7]]
```

- 5、slice()：返回数组的一个片段或者子数组，不改变原数组

``` js
//第一个参数为起始位置
//第二个参数为结束位置
//左闭右开
//负数为倒数
let a = [1, 2, 3, 4, 5];
let b = a.slice(0, 3); // => [1, 2, 3]
let c = a.slice(3); // => [4, 5]
let d = a.slice(1, -1); // => [2, 3, 4]
let e = a.slice(-3, -2); // => [3]
```

- 6、splice()：数组中插入或删除元素的通用方法

``` js
//第一个参数指定了插入或删除的起始位置
//第二个参数指定了从起始位置删除元素的个数
//后面的任意个数参数，都将从起始位置插入数组
//splice()删除
let arrayTest = [1, 2, 3, 4, 5, 6, 7, 8, 9];
arrayTest.splice(4); //返回[5, 6, 7, 8, 9]; arrayTest 是[1, 2, 3, 4]
arrayTest.splice(1, 2); //返回[2, 3]; arrayTest 是[1, 4]
//splice()增加
let arrayTest = [1, 2, 3, 4, 5];
arrayTest.splice(2, 0, 'a', 'b'); //返回[]; arrayTest 是[1, 2, 'a', 'b', 3, 4, 5]
arrayTest.splice(2, 2, [1, 2], 3); //返回['a', 'b']; arrayTest 是[1, 2, [1, 2], 3, 3, 4, 5]
```

- 7、push() 和 pop()

``` js
let test = [];
//push(): 在数组尾部插入一个或多个元素，返回数组新长度
test.push('amazing'); 
test.push('one', 'two');
//pop(): 删除数组的最后一个元素，减小数组长度并返回它删除的值
test.pop();
```

- 8、unshift() 和 shift()

``` js
let test = [];
//unshift(): 在数组头部插入一个或多个元素，返回数组新长度
test.unshift('amazing');
test.unshift('one', 'two');
//shift(): 删除数组的第一个元素，减小数组长度并返回它删除的值
test.shift();
```

- 9、toString() 和 toLocaleString()

``` js
//这里不做介绍
```



###### ES5

- 1、forEach()

``` js
//
```

- 2、map()

``` js
//
```

- 3、filter()

``` js
//
```

- 4、every() 和 some()

``` js
//
```

- 5、reduce() 和 reduceRight()

``` js
//
```

- 6、indexOf() 和 lastIndexOf()

``` js
//
```



##### 100、稀疏数组不做介绍

##### 101、多维数组不做介绍

##### 102、类数组对象不做介绍



