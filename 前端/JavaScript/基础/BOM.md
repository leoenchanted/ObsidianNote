# 概述
BOM比DOM更大，包含着DOM
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1674187762915-477b5797-d566-4608-8dd9-9d54d1d1f0e0.png#averageHue=%23f8fcf9&clientId=ue8c85e17-a124-4&from=paste&height=259&id=ufa3db12e&originHeight=330&originWidth=1148&originalType=binary&ratio=1&rotation=0&showTitle=false&size=92922&status=done&style=none&taskId=u3d8bf8ba-e03d-462b-bdfe-dfc36f24d3f&title=&width=900.3921736996253)
## BOM的构成
**window对象是浏览器的顶级对象**，它具有双重角色。

1. 是js访问浏览器窗口的一个接口
2. 是一个全局对象，定义在全局作用域中的变量，函数都会变成我window对象的属性和方法。

调用的时候可以省略window，前面学习的对话框都属于window对象方法
**注意：window下的一个特殊属性 window.name**
# window对象的常见事件
## 页面加载事件
### 窗口加载
window.onload是窗口加载事件，当文档内容完全加载完成会触发事件**（包括图像、脚本文件、CSS文件等）**，就调用的处理函数
注意：

1. window.onload只能写一次，写多个，以最后一个为准。
2. 使用addEventListener 则没有限制。
```javascript
window.addEventListener('load',function(){});
```


```javascript
document.addEventListener('DOMContentLoaded',function(){});
```
这个事件触发时，仅当DOM加载完成，不包括样式表，图片，flash等
页面图片很多的话，可以用这个事件比较适合
## 调整窗口大小事件
```javascript
window.addEventListener("resize",function(){});
```
注意：

1. 只要窗口大小发生像素变化，就会触发这个事件。
2. 我们经常利用这个事件完成响应式布局，window.innerWidth当前屏幕的宽度。

# 定时器
## 两种定时器
### setTimeout()定时器
```javascript
window.setTimeout(调用函数,延时时间[毫秒]);
```
**window在调用的时候可以省略**
### 停止setTimeout()定时器
```javascript
window.clearTimeout(timeoutID);
```

- window可以省略
- 里面的参数是定时器的标识符
### setInterval()定时器
```javascript
window.setInterval(回调函数,[间隔的毫秒数]);
```
重复调用一个函数，每隔这个时间，就去调用一次回调函数
### 停止setInterval()定时器
```javascript
window.clearInterval(intervalID);
```

- window可以省略
- 里面的参数是定时器的标识符
## 额外 requestAnimationFrame
这个可以说是类似定时器的，他是一帧一帧来的，60帧每1000毫秒，1帧就是16.67毫秒，相当于定时器那个延迟时间是17。
例子
```javascript
        let canvas = document.getElementById("canvas");
        let cxt = canvas. getContext("2d");
        var ball = new Ball(100,canvas.height/2,20,"pink");
        var vx =2;
       function frame(){
        cxt.clearRect(0,0,canvas.width,canvas.height);
        ball.x+=vx;
        ball.fill(cxt);
        window.requestAnimationFrame(frame);
       }
       window.requestAnimationFrame(frame);   //用递归的方法让他一直运动下去。
```
# JS执行机制
## JS是单线程

- JavaScript语言一大特点是单线程，同一个时间只能做一件事
- 这样就意味着，所有任务都需要排队，从而导致问题：JS的执行时间过长，这样就会造成页面的渲染不连贯，导致页面渲染加载阻塞的感觉
## 同步和异步
### 同步
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1675227360206-05013e8c-41bf-43e6-ab7b-71711a39f515.png#averageHue=%23e8ebe8&clientId=u3d93a4c1-08ca-4&from=paste&height=78&id=u4bd49d52&originHeight=99&originWidth=1277&originalType=binary&ratio=1&rotation=0&showTitle=false&size=95354&status=done&style=none&taskId=u6f5279d9-7630-46b8-9ad7-d1733302ac0&title=&width=1001.5686461798097)
### 异步
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1675227378369-ca7b1eae-2584-4548-8244-4c8f5a957885.png#averageHue=%23eaedea&clientId=u3d93a4c1-08ca-4&from=paste&height=100&id=u0988682d&originHeight=127&originWidth=1252&originalType=binary&ratio=1&rotation=0&showTitle=false&size=104882&status=done&style=none&taskId=u58dc6901-6d77-4a8a-825d-c5c90ed7fda&title=&width=981.960802675898) 
### 同步任务

- 同步任务都在主线程上执行，形成一个执行栈
### 异步任务

- JS的异步是通过回调函数实现的
- 一般而言，异步任务有以下三种类型
1. 普通事件，例如click,resize
2. 资源加载，例如load,error
3. 定时器，例如setInterval,setTimeout

异步任务相关回调函数添加到**任务队列**中（任务队列也称为消息队列）
## JS执行机制

1. W先执行执行栈中的同步任务。
2. 异步任务（回调函数）放入任务队列中
3. 一旦执行栈中的所有同步任务执行完毕，系统就会按次序开始读取**任务队列**中的异步任务，于是被读取的异步任务结束等待状态，进入执行栈，开始执行。

![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1675237358321-67f083e2-4646-4e0f-90b8-7fb672931845.png#averageHue=%23fcfdfc&clientId=u7b139765-e9d8-4&from=paste&height=173&id=ua6ae6771&originHeight=346&originWidth=888&originalType=binary&ratio=1&rotation=0&showTitle=false&size=62189&status=done&style=none&taskId=ubb3b3e58-4c3c-4f2f-8cdd-ca6a2e05a0e&title=&width=444)
# location对象
## 什么事location对象

- 用于获取或设置窗体的URL，并且可以用于解析URL。
## location对象的属性
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1675237758658-40c5387a-219d-436e-b0ba-ede7ebc0ff53.png#averageHue=%23f9faf9&clientId=u7b139765-e9d8-4&from=paste&height=192&id=u42f7f7af&originHeight=383&originWidth=1048&originalType=binary&ratio=1&rotation=0&showTitle=false&size=170191&status=done&style=none&taskId=u7806be23-8370-49a5-bb81-7650711b55a&title=&width=524)
# history对象
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1675875454686-11125268-ee23-4ab1-839e-b241e35d60a7.png#averageHue=%23f6f9f6&clientId=u7dca6a37-717c-4&from=paste&height=419&id=u0c2e900d&originHeight=534&originWidth=1448&originalType=binary&ratio=1&rotation=0&showTitle=false&size=188600&status=done&style=none&taskId=u21382922-998f-4a1e-a8dd-85ebce343d1&title=&width=1135.6862957465657)
一般较少用
# 

