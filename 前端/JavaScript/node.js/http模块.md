# 创建http服务端
```javascript
//导入模块
const http = require('http');

//创建服务对象
const server = http.createServer((request,reponse)=>{
  reponse.end('Hello HTTP Server'); //设置响应体
});

//监听端口，启动服务
server.listen(9000,()=>{
  console.log('服务已经启动...');
})
```
## HTTP服务的注意事项
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1689317451743-68c9e139-fae7-4130-b867-0f4d5e6a8474.png#averageHue=%23e7dfd8&clientId=uf3d3214c-d28f-4&from=paste&height=638&id=u2dcd326a&originHeight=814&originWidth=1449&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=309389&status=done&style=none&taskId=u5e8622a1-58bc-492e-948b-2a96dfa4a66&title=&width=1136.4706094867222)
# 获取请求
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1689321690715-09ff5e37-9e39-4db1-afa0-e15a9ff66bc1.png#averageHue=%2334342b&clientId=uf3d3214c-d28f-4&from=paste&height=314&id=ubb934acd&originHeight=400&originWidth=964&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=265164&status=done&style=none&taskId=u1611929c-541b-41c4-b310-2306ffb86c0&title=&width=756.0784455108352)
# GET请求和POST请求场景区别
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1689574716266-8fe427c8-bc0f-4090-ba56-326f2b9c34d1.png#averageHue=%23fdfdfd&clientId=u93d1fa66-5632-4&from=paste&height=507&id=ued09768d&originHeight=646&originWidth=994&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=163456&status=done&style=none&taskId=u64d50f41-c737-4366-8da8-17671941d28&title=&width=779.6078577155292)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1689574747200-ccdbf1c8-8754-469e-8f14-3e93aa583588.png#averageHue=%23e7e2de&clientId=u93d1fa66-5632-4&from=paste&height=261&id=u1ff967ea&originHeight=333&originWidth=1170&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=196833&status=done&style=none&taskId=u76f45f13-2cd1-4d72-89c9-5c672525c6f&title=&width=917.6470759830676)
# MIME类型
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1689662780112-dd121abb-14aa-4542-92a3-6a4d3f218dff.png#averageHue=%23dfe6eb&clientId=u3aefbd40-eef8-4&from=paste&height=438&id=ub5adf431&originHeight=559&originWidth=1265&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=190877&status=done&style=none&taskId=u82d54303-d386-4ee2-8c54-86468b7c51a&title=&width=992.156881297932)
# 进行响应
```javascript
const http = require('http');
const fs = require('fs');
const server = http.createServer((req,res)=>{
    //获取请求的url的路径
    let {pathname} = new URL(req.url,'http://127.0.0.1');    //后面那个参数是类似于说前面的一样对照？
    if(pathname === '/'){
        let html = fs.readFileSync(__dirname + '/index.html');
        res.end(html);
    }else if(pathname === '/style.css'){
        let css = fs.readFileSync(__dirname + '/style.css');
        res.end(css);
    }else if(pathname === '/script.js'){
        let js = fs.readFileSync(__dirname + '/script.js');
        res.end(js);
    }else{
        res.statusCode = 404;
        res.end('<h1>404 not found </h1>');
    }
});

server.listen(9000,()=>{
    console.log('succeess');

})
```
