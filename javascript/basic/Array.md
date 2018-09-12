## Array



##### 1、数组是对象的特殊形式

##### 2、创建

```js
let test = [];
```

##### 2、读写

```js
test[0] = 'hello world';
let str = test[0];
```

##### 3、属性

- length

``` js
let num = test.length;
let num = [].length;
```

##### 4、添加和删除

- delete: 删除指定元素的值，位置保留，值变为undefined

``` js
delete test[0];
```

- push() 和 pop() ==> 8、数组方法里面有介绍
- unshift() 和 shift() ==> 8、数组方法里面有介绍
- splice() ==> 8、数组方法里面有介绍

##### 5、遍历

- for

``` js
let arrayTest = [1, 2, 3, 4, 5];
for (let i = 0; i < arrayTest.length; i++) {
    let value = arrayTest[i];
    //可以break
    //可以continue
}
```

- for of

``` js
let arrayTest = [1, 2, 3, 4, 5];
for (let item of arrayTest) {
    let value = arrayTest[item];
    //可以break
    //可以continue
    //只读
}
```

- foreach() ==> 8、数组方法里面有介绍
- map() ==> 8、数组方法里面有介绍

##### 6、作为数组的字符串

``` js
let str = 'test';
str.charAt(0); // => 't'
str[1]; // => 'e'
```

##### 7、判断数组类型

- (ES5中) Array.isArray() 来判断未知的对象是否为数组

``` js
Array.isArray([]); // => true
Array.isArray({}); // => fasle
```

##### 8、数组方法

- ES3

``` js
//1、join()
	//将数组所有元素以分隔符的形式转化为字符串，不指定分隔符，默认为逗号
	let arrayTest = [1, 2, 3];
	arrayTest.join(); // => "1,2,3"
	arrayTest.join(" "); // => "1 2 3"
	arrayTest.join(""); // => "123"
	let b = new Array(10);
	b.join('-'); // => "---------" 9个
//2、reverse()
	//逆序
	let a = [1, 2, 3];
	a.reverse(); // => a 是 [3, 2, 1]  a 本身改变
//3、sort()
	//排序
	
//4、concat()
//5、slice()
//6、splice()
    //splice(): 数组中插入或删除元素的通用方法
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
//7、push() 和 pop()
    let test = [];
    //push(): 在数组尾部插入一个或多个元素，返回数组新长度
    test.push('amazing'); 
    test.push('one', 'two');
    //pop(): 删除数组的最后一个元素，减小数组长度并返回它删除的值
    test.pop();
//8、unshift() 和 shift()
    let test = [];
    //unshift(): 在数组头部插入一个或多个元素，返回数组新长度
    test.unshift('amazing');
    test.unshift('one', 'two');
    //shift(): 删除数组的第一个元素，减小数组长度并返回它删除的值
    test.shift();
//9、toString() 和 toLocaleString()
```

- ES5

``` js
//1、forEach()
//2、map()
//3、filter()
//4、every() 和 some()
//5、reduce() 和 reduceRight()
//6、indexOf() 和 lastIndexOf()
```



##### 100、稀疏数组不做介绍

##### 101、多维数组不做介绍

##### 102、类数组对象不做介绍



