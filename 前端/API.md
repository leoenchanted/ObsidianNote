
```javascript
 var canvas = document.getElementById("canvas");
 var ctx = canvas.getContext("2d");  //获取上下文 获取画笔

 ctx.beginPath();   //开始绘制 绘制分开的线在前面加上这一个可以分开
 ctx.closePath();  //与begin包裹起来，可以闭合好？

 ctx.moveTo();   //移动画笔
 ctx.lineTo();    //笔画停点
 ctx.lineWidth = 2;   画笔粗细
 ctx.strokeStyle = "";   //画笔颜色
 ctx.fillStyle = "";    //填充颜色
 ctx.stroke();    //描边
 ctx.fill();    //填充
```
# API
## rect()方法绘制矩形
canvas API已经帮我们封装好绘制矩形的方法，rect（） 。接受4个参数x,y,width,height<br />前面写beginPath 写这个方法 不用写closePath了
## arc() 绘制圆弧路径
```javascript
void ctx.arc(x, y, radius, startAngle, endAngle, anticlockwise);
```
x<br />圆弧中心（圆心）的 x 轴坐标。<br />y<br />圆弧中心（圆心）的 y 轴坐标。<br />radius<br />圆弧的半径。<br />startAngle<br />圆弧的起始点，x 轴方向开始计算，单位以弧度表示。<br />endAngle<br />圆弧的终点，单位以弧度表示。<br />anticlockwise 可选<br />可选的[Boolean](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Boolean)值，如果为 true，逆时针绘制圆弧，反之，顺时针绘制。
### arcTo()
使用当前的描点 (前一个 moveTo 或 lineTo 等函数的止点)。根据当前描点与给定的控制点 1 连接的直线，和控制点 1 与控制点 2 连接的直线，作为使用指定半径的圆的**切线**，画出两条切线之间的弧线路径。
```javascript
void ctx.arcTo(x1, y1, x2, y2, radius);
```
## 贝塞尔曲线绘制
### 二次贝塞尔曲线
它需要 2 个点。第一个点是控制点，第二个点是终点。起始点是当前路径最新的点
```javascript
void ctx.quadraticCurveTo(cpx, cpy, x, y);
```
### 三次贝塞尔曲线
该方法需要三个点。第一、第二个点是控制点，第三个点是结束点。起始点是当前路径的最后一个点
```javascript
void ctx.bezierCurveTo(cp1x, cp1y, cp2x, cp2y, x, y);
```
# 线条属性
## lineCap   线条的帽子

- butt：默认值，端点是垂直于线段边缘的平直边缘。
- round：端点是在线段边缘处以线宽为直径的半圆。   （相当于线条两端变圆角）
- square：端点是在选段边缘处以线宽为长、以一半线宽为宽的矩形。   （变矩形角）
## lineJoin  线条的连接

- miter：默认值，在连接处边缘延长相接。miterLimit 是角长和线宽所允许的最大比例(默认是 10)。
- bevel：连接处是一个对角线斜角。
- round：连接处是一个圆。
# 渐变
## 线性渐变
三步走战略：

1添加渐变线：

```javascript
vargrd=context.createLinearGradient(xstart,ystart,xend,yend);
```
<br />1为渐变线添加关键色(类似于颜色断点)：

```javascript

grd.addColorStop(stop,color);
```
<br />这里的stop传递的是 0 ~ 1 的浮点数，代表断点到(xstart,ystart)的距离占整个渐变色长度是比例。

1应用渐变：

```javascript

context.fillStyle=grd;
context.strokeStyle=grd;
```
## 径向渐变
区别就是添加渐变线
```javascript
var grd = context.createRadialGradient(x0,y0,r0,x1,y1,r1);
```
# 变换
## 平移变换
`translate(x,y)`<br />![](https://cdn.nlark.com/yuque/0/2023/jpeg/anonymous/1696920443107-6851bff0-4ac7-4d14-ac66-679bb605ceee.jpeg#averageHue=%23978e83&id=IUyTf&originHeight=474&originWidth=3762&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)<br />![](https://cdn.nlark.com/yuque/0/2023/jpeg/anonymous/1696920483431-aa6852df-8584-44c0-86d2-2703c2786053.jpeg#averageHue=%23a0958b&id=Yo5yF&originHeight=1280&originWidth=2022&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)
### 注意使用状态保存
用`ctx.save()`和`ctx.restore()`进行保存和充值坐标状态？
## 旋转变换
`rotate(deg)`<br />角度用弧度来表示，例如180°应写成Math.PI。注：一般以坐标0点为旋转中心进行旋转
## 缩放变换
`scale(sx,sy)`<br />x表示图形再x轴方向的缩放倍数。y表示图形再y轴方向的缩放倍数。<br />负作用：除了会改变图形的大小之外，还会改变其他属性，如线条宽度、左上角坐标等。
## 矩阵变换
`transform(a,b,c,d,e,f)`

| 参数 | 意义 |
| --- | --- |
| a | 水平缩放 |
| b | 水平倾斜 |
| c | 垂直倾斜 |
| d | 垂直缩放 |
| e | 水平位移 |
| f | 垂直位移 |


