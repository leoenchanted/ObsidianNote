DOM是文档对象模型（Document Object Model），是W3C组织推荐的处理可扩展标记语言的标准编程接口
# 获取元素
## 根据ID获取

- 使用getElementById() 可以获取带有ID的元素对象
## 根据标签名获取

- 使用getElementByTagName() 返回带有指定标签名的对象的集合

还可以获取某个元素（父元素）内部所有指定标签名的子元素
```javascript
document.getElementByTagName('标签名')；
```
父元素必须是单个对象（必须指明是哪一个元素对象）  获取的时候不包括父元素自己
## H5新增获取方法
```javascript
document.getElementsByClassName('类名'); //根据类名返回
document.querySelector('选择器')；  //根据指定选择器返回第一个元素对象
ducument.querySelectorAll('选择器')； //返回指定选择器所有元素对象集合
```
[[className和classList]]
## 获取body和html元素
### body
document.body;
### html
document.documentElement;
# 事件基础
事件有三部分组成  事件源  事件类型 事件处理程序
```javascript
<button id='btn'>呵呵</button>

//1.事件源  事件被触发的对象
var btn = document.getElementById('btn');
//2.事件类型  如何触发    如鼠标点击（onclick） 还是经过还是键盘按下
//3.事件处理程序   通过函数赋值的方式  完成
btn.onclick = function(){
  alert('呵呵');
}
  
```
## 执行事件的步骤

1. 获取事件源
2. 注册事件（绑定事件）
3. 添加事件处理程序（采取函数赋值形式）
## 常见鼠标事件
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1673082015575-6acddddd-99fb-426d-8257-a9d3ec121d81.png#averageHue=%23f6f9f6&clientId=u52069fc6-50a3-4&from=paste&height=264&id=ud6b2f90c&originHeight=268&originWidth=568&originalType=binary&ratio=1&rotation=0&showTitle=false&size=43071&status=done&style=none&taskId=ua564847a-3e7d-4d8d-9f36-b1b7292c095&title=&width=560.4902038574219)
# 操作元素
## 改变元素内容
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1673082199304-49223b82-4a8a-42e1-9612-19f1a5d7604e.png#averageHue=%23f6f9f7&clientId=u52069fc6-50a3-4&from=paste&height=148&id=u8807fe31&originHeight=155&originWidth=575&originalType=binary&ratio=1&rotation=0&showTitle=false&size=23644&status=done&style=none&taskId=uc70f4422-9c34-4961-b46a-6abc7a0c361&title=&width=549.9804077148438)
innerHTML可以识别html标签
## 常用元素的属性操作
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1673082367097-7b8f7b76-7f56-4668-a953-53fdd5cf970d.png#averageHue=%23e1ecfb&clientId=u52069fc6-50a3-4&from=paste&height=156&id=u5f7190ad&originHeight=125&originWidth=410&originalType=binary&ratio=1&rotation=0&showTitle=false&size=8965&status=done&style=none&taskId=uc717cf1e-e6fa-4fc9-a167-93a2414b1bf&title=&width=512.5686340332031)
[[innerText、innerHTML、textContent]]

## 表单元素的属性操作
操作如下表单元素：  type、value、checked、selected、disabled
## 样式属性操作
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1673083692337-b4647643-e413-45c3-b552-1d4746c0c538.png#averageHue=%23fafdfa&clientId=u52069fc6-50a3-4&from=paste&height=236&id=ub805c353&originHeight=525&originWidth=1334&originalType=binary&ratio=1&rotation=0&showTitle=false&size=152459&status=done&style=none&taskId=u84077a2b-022b-4cff-b06a-b1c4c5fb05f&title=&width=598.691162109375)
```javascript
//例如
element.style.backgroungColor = '';
```
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1673084041195-792d5548-77c1-48e5-9285-3fd20e02ebb6.png#averageHue=%23fbfefb&clientId=u52069fc6-50a3-4&from=paste&height=231&id=u29e0c755&originHeight=295&originWidth=918&originalType=binary&ratio=1&rotation=0&showTitle=false&size=100636&status=done&style=none&taskId=u59ee0b97-d333-4c76-bf42-ffe9f5617ff&title=&width=720.0000134636376)
## 自定义属性的操作
### 1. 获取属性值
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1673148977774-bf098681-be24-4a3e-85c7-86352361d489.png#averageHue=%23f2f5f2&clientId=u51c387ef-7ad3-4&from=paste&height=125&id=u93d95086&originHeight=160&originWidth=1365&originalType=binary&ratio=1&rotation=0&showTitle=false&size=74706&status=done&style=none&taskId=u770cfd77-5f72-4180-a1a0-3ad4214e6f2&title=&width=1070.5882553135789)
### 2.设置属性值
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1673149065048-776877a6-9e62-4555-94bd-23d129649340.png#averageHue=%23f5f8f5&clientId=u51c387ef-7ad3-4&from=paste&height=135&id=u0ecd07f9&originHeight=172&originWidth=669&originalType=binary&ratio=1&rotation=0&showTitle=false&size=41644&status=done&style=none&taskId=ucd1ce4d1-c941-4057-abee-c2cea7e9799&title=&width=524.7058921646772)
### 3.移除属性值
removeAttribute(属性);
## h5自定义属性新增
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1673153417075-d9741784-a89d-493a-997d-36e6b16af1d6.png#averageHue=%231f221f&clientId=u51c387ef-7ad3-4&from=paste&height=338&id=ua8ebc416&originHeight=283&originWidth=523&originalType=binary&ratio=1&rotation=0&showTitle=false&size=143450&status=done&style=none&taskId=u59223ed0-dff2-4e51-b2b6-9e388f2d545&title=&width=625.1960754394531)
# 节点操作
获取元素通常使用两种方式：

1. 利用DOM提供的方法获取元素
- getElementById  getElementByTagName  querySelector
- 逻辑性不强、繁琐
2. 利用节点层级关系或许元素
## 节点概述
节点至少拥有nodeType（节点类型）、nodeName（节点名称）和nodeValue（节点值）这三个基本属性

- 元素节点 nodeType为1
- 属性节点nodeType为2
- 文本节点nodeType为3 （文本节点包含文字、空格、换行等）

实际开发中，节点操作主要操作的是**元素节点  **
## 节点层级
### 1.父级节点
```javascript
node.parentNode
```

- parentNode属性可以返回某节点的父节点，注意是最近的一个父节点，相当于亲爸爸
- 如果指定的节点没有父节点则返回null
### 2.子级节点
```javascript
1.  parentNode.childNodes  //标准
```
注意：返回值包含所有的子节点，包括元素节点，文本节点等
如果只想获得里面的元素节点，需要专门处理，所以一般不提倡使用childNodes
```javascript
2.   parentNode.children  //非标准
```
只是一个只读属性
#### 第一个和最后一个孩子
firstChild  和lastChild   所有节点 
元素节点则是  firstElementChild 和 lastElementChild   这个有兼容性问题
### 兄弟节点
```javascript
 1.  node.nextSibling  //下一个兄弟节点
 2.  node.previousSibling  //上一个兄弟结点
```
同样，也是会返回包含**所有的结点**
```javascript
3. node.nexeElementSibling  
4. node.previousElementSibling
```
同样，这样的话也会有兼容性问题
### 创建节点
```javascript
document.createElement('tagName')
```
### 添加节点
```javascript
note.appendChild(child)    //node父级  child子级
```
这种方法是将一个节点添加到指定父节点的子节点列表末尾，类似css里面after伪元素
```javascript
note.insertBefore(child,指定元素)
```
这种方法是一个节点添加到父节点的指定子节点前面，类似before伪元素
### 删除节点
```javascript
node.removeChild(child)
```
### 复制节点（克隆节点）
```javascript
node.cloneNode()
```
注意：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1673158016174-a199b2f5-48d2-4a40-b94b-17c0595095f8.png#averageHue=%23f2f5f2&clientId=u9bd1f933-03bf-4&from=paste&height=140&id=ua58f759c&originHeight=179&originWidth=1329&originalType=binary&ratio=1&rotation=0&showTitle=false&size=117005&status=done&style=none&taskId=u46cd80a4-de03-4765-825a-60530dd15c9&title=&width=1042.352960667946)
