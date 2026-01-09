除了矩形，其他所有canvas基本图形，包括直线、多边形、圆形、弧线、贝塞尔曲线，都是以路径为基础的。

| 方法 | 说明 |
| --- | --- |
| beginPath() | 开始一条新的路径 |
| closePath() | 关闭当前路径 |
| isPointlnPath() | 判断某一个点是否存在于当前路径内 |
## beginPath()
总结以下4点
+ 如果画出来的图形跟预期不一样，记得检查一下是否有合理地使用beginPath()方法。
+ 判断开始一个新路径的唯一标准是“是否使用beginPath()方法”，而不是视觉上的首尾相连。
+ 使用以下方法只是绘制图形，并不会开始新路径:moveTo()、lineTo()、strokeRect()、fillRect()、rect()、arc()、arcTo()、quadricCurveTo()和bezierCurveTo()。
+ canvas中的绘制方法，如stroke()、fill()等，都是以“之前最近的beginPath()”后面所有定义的状态为基础进行绘制的。
## closePath()
总结以下4点
+ closePath()是==关闭路径== ，并不是==结束路径== 。关闭路径，指的是连接起点与终点；结束路径，指的是开始新的路径。
+ 如果canvas只有一条线段的话，那么closePath()方法就什么都不做。
+ 在canvas中，只有beginPath()这一种方法可以开始新的路径。判断新路径的唯一标准是为“是是否使用beginPath()”。
+ closePath()方法主要用于实现“封闭图形”，例如三角形、多边形、圆形、扇形等。然后，我们才能使用fill()方法来进行填充操作。
## isPointlnPath()
用这个方法来判断某一个点是否存在于当前的路径中
`ctx.isPointlnPath(x,y)`
如果点(x,y)位于当前路径中，返回true；否则返回false