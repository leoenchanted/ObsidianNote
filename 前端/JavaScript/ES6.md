## 新增let、const
## 解构赋值
ES6允许从数组中提取值，按照对应位置，对变量赋值，对象也可以实现解构
### 数组解构
```javascript
let [a.b.c] = [1,2,3];
console.log(a);
console.log(b);
console.log(c);
```
### 对象解构
```javascript
let person = {name:'zhangsan',age:20};
let {name,age} = person;
console.log(name);
console.log(age);
```
## 箭头函数
```javascript
() => {}
const fn = () => {}
```
例子
```javascript
function sum(num1,num2){
  return num1+num2;
}
//可以转换为    如果函数体只有一句代码，并且代码的执行结果就是函数的返回值 函数体
//大括号可以省略
const sum = (num1,num2) => num1+num2;
```
箭头函数不绑定this关键字，箭头函数中的this，指向的是**函数定义位置的上下文this**
**箭头函数不能用argument**
## 剩余参数
使用三个点（...）将函数的最后一个参数表示为一个数组，该数组包含了函数调用时传入的所有参数
## Array的扩展方法
### 扩展运算符
和剩余参数相似，作用却相反   用于将一个数组或对象展开成多个独立的元素
```javascript
let array1 = [1,2,3];
let array2 = [4,5,6];
let merged = [...array1,...array2];
console.log(merged);  //输出[1,2,3,4,5,6]
```
### 构造函数方法： Array.from()
### 实例方法：find()
find用于查找数组中符合条件的第一个元素
```javascript
let array = [1,2,3,4,5];
let result = array.find(function(element){
  return element >3 ;
});
console.log(result); //输出4

//只会查找符合条件的第一个元素
//返回的是元素的值，而不是元素的索引    获取元素索引用findIndex()
```
### includes()
返回 true和false
## String扩展方法
### 模板字符串
新的拼接字符串方法 传统是用+连接字符串
```javascript
let name = "Tom";
let age = 18;
let message = `My name is ${name},and I'm ${age} years old.`;
console.log(message); //输出My name is Tom,and I'm 18 years old.

//模板字符串使用反引号``包裹起来
```
### starsWith() endsWith()
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1680009748967-0a66df3a-8126-49ba-b201-f7ba51a80449.png#averageHue=%2391b6a5&clientId=u59a0fd79-6b55-4&from=paste&height=279&id=u217c62d6&originHeight=356&originWidth=1393&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=116499&status=done&style=none&taskId=ufc3263bc-47b9-4745-8737-15475517d7d&title=&width=1092.54904003796)
### repeat()
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1680009776970-a54f524e-544e-4fe9-b795-cdb29a84c3ab.png#averageHue=%2389b19b&clientId=u59a0fd79-6b55-4&from=paste&height=190&id=u98444237&originHeight=242&originWidth=1257&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=63218&status=done&style=none&taskId=u7ad0f319-ba9a-4ce6-9444-906b0c21489&title=&width=985.8823713766803)
## Set数据结构
类似于数组，但是成员的值都是唯一的，没有重复的值
Set 本身是一个构造函数，用来生成Set数据结构
```javascript
const s = new Set();
//可以接受一个数组作为参数，用来初始化
const set = new Set([1,2,3,4,4]);  //size代表有几个值
```
### 实例方法
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1680011943453-eecfffca-3502-4ef6-877f-d07fe076f3de.png#averageHue=%2382b195&clientId=u59a0fd79-6b55-4&from=paste&height=377&id=u499c9b70&originHeight=481&originWidth=1295&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=219850&status=done&style=none&taskId=uca82f886-610d-4cd3-b96e-a3fe111076b&title=&width=1015.6862935026261)
### 遍历
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1680011974351-ec952794-b5ce-49f2-8a45-44cf48e3f99e.png#averageHue=%23f3f4f9&clientId=u59a0fd79-6b55-4&from=paste&height=190&id=u30488b2c&originHeight=242&originWidth=1359&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=68244&status=done&style=none&taskId=ucf63991f-77ee-4a22-9715-45b59bfda0c&title=&width=1065.88237287264)
