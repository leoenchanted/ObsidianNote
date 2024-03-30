# express路由
## 什么是路由？
路由确定了应用程序如何响应客户端对特定端点的请求
## 路由的使用
一个路由的组成有请求方法，路径和回调函数组成
使用格式如下
`app.<method>(path,callback)`
## 获取请求参数
express框架封装了一些API来方便获取请求报文中的数据，并且兼容原生HTTP模块的获取方式
```javascript
const express = require('express');
const app = express();
app.get('/home',(req,res)=>{
    //原生操作
    console.log(req.method);
    console.log(req.url);
    console.log(req.httpVersion);
    console.log(req.headers);

    //express操作
    console.log(req.path);
    console.log(req.query);
     //获取ip
     console.log(req.ip);


    res.end('Lavender');
})
app.listen(3000,()=>{
    console.log('启动成功');
})
```
## 获取路由参数
路由参数指的是URL路径中的参数（数据）
```javascript
app.get('/:id.html',(req,res)=>{     //:id 前面就可以写任何数字了
  res.end('商品id为' + req.params.id);     //params.id 获取参数字符串  id和上面占位符要一样
})
```
## express响应设置
express框架封装了一些API来方便给客户端响应数据，并且兼容原生HTTP模块的获取方式

```javascript
const express = require('express');
const app = express();
app.get('/response',(req,res)=>{
    //原生操作
  res.statusCode = 404;
  res.statusMessage = 'love';
  res.setHeader('xxx','yyy');
  res.write('hello express');
  res.end('response');

    //express操作
  res.status(500);
  res.set('aaa','bbb');
  res.send('你好 haa');   //这个send 自动给响应体加了不会中文乱码的那个头
     //链式调用
  res.status(500).set('abc','def').send('nih ha');


})
app.listen(3000,()=>{
    console.log('启动成功');
})
```
 res.send('你好 haa');   //这个send 自动给响应体加了不会中文乱码的那个头
### 其他响应
```javascript
res.redirect('http://baidu.com');  //重定向 相当于跳转
res.download('./package.json');    //下载响应
res.json();  //响应json
res.sendFile(__dirname + '/home.html');   //响应文件内容 直接读取html了
```
## 中间件
### 什么是中间件
本质是一个回调函数
### 作用
使用函数封装公共操作，简化代码
### 类型

- 全局中间件
- 理由中间件
### 定义全局中间件
每一个请求到达服务器之后都会执行全局中间件函数
> 插播一下 path.resolve的用法  如果参数斜杠开头则说明绝对路径 第一第二个参数都有则忽略第一个  而且path.resolve()返回的是当前工作目录的绝对路径 即你在终端执行代码的那个路径  path.resolve(__dirname)返回的是当前模块的绝对路径 则是这个代码所在的

声明中间件函数
```javascript
const express = require('express');
const fs = require('fs');
const path = require('path');
const app = express();
//声明中间件函数
const middleWare = (req,res,next)=>{
    let{url,ip} = req;
    //将信息保存再文件中access.log
    fs.appendFileSync(path.resolve(__dirname,'./access.log'),`${url}  ${ip}\r\n`);
    next();  //调用next()将控制权传递给下一个中间件或请求处理函数

}
app.use(middleWare);
app.get('/home',(req,res)=>{

    res.send('泰勒斯威夫特');
})
app.get('/login',(req,res)=>{

    res.send('泰勒斯威夫特登录');
})
app.get('/regin',(req,res)=>{

    res.send('泰勒斯威夫特注册');
})
app.listen(3000,()=>{
    console.log('启动成功');
})

```
### 路由中间件实践
```javascript
//针对 /admin /setting 的请求，要求 URL 携带 cqde=521 参数，如未携带提示[暗号错误]

const express = require('express');
const app = express();
//声明中间件函数
const middleWare = (req,res,next)=>{
    if(req.query.code === '521'){
        next();       //这个如果成功了就会调到中间件那个函数，不然直接写很多地方显示得的send不一样
    }else{
        res.send('暗号错误');
    }

}

app.get('/home',middleWare,(req,res)=>{

    res.send('前台首页');
})
app.get('/admin',middleWare,(req,res)=>{

    res.send('后台页面');
})
app.get('/setting',middleWare,(req,res)=>{

    res.send('设置页面');
})
app.listen(3000,()=>{
    console.log('启动成功');
})

```
### 静态资源中间件设置
直接一行代码
`app.use(express.static(__dirname+'/public'));`
#### 静态资源中间件注意点
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1689873201061-0b1bff1e-158f-475b-bf64-3793abc6999f.png#averageHue=%23e3efea&clientId=u95cb08b8-5684-4&from=paste&height=171&id=u90443e55&originHeight=218&originWidth=873&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=117017&status=done&style=none&taskId=u93579010-40bb-4386-a475-f454efced71&title=&width=684.7058951565966)
