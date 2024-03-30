fs模块可以实现与硬盘的交互，例如文件的创建、删除、重命名、移动，还有文件内容的写入、读取，以及文件夹的相关操作
# 写入文件
首先
```javascript
const fs = require('fs');
fs.wirteFile('./t.txt','content',err=>{
  if(err){
    console.log('defeat');
    return;}
    console.log('victory');
  )
```
## 同步
```javascript
//同步写入
fs.writeFileSync('./data.txt','test');
```
## 追加写入
appendFile/appendFileSync
在文件尾部追加内容，appendFile语法和writeFile语法完全相同
## CreateWriteStream 流式写入
```javascript
const fs = require ('fs');
let ws = fs.createWriteStream('./sdf.txt');
ws.write('Midnigts\r\n');
ws.write('Midnigts\r\n');
ws.write('Midnigts\r\n');
ws.write('Midnigts\r\n');
ws.close();
```
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1689152289759-c22d399b-7dbc-45ff-ae9e-e3d3e2c90f5f.png#averageHue=%23e7f1ec&clientId=u9c20a7d3-8c6a-4&from=paste&height=94&id=u25d50301&originHeight=120&originWidth=841&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=68003&status=done&style=none&taskId=u028956d7-5d24-472e-be11-e58c09e53c3&title=&width=659.6078554715896)
## 文件写入的场景

- 下载文件
- 安装软件
- 保存程序日志，如Git
- 编辑器保存文件
- 视频录制

当需要持久化保存数据的时候，应该想到文件写入
# 文件读取
```javascript
const fs = require('fs');
fs.readFile('./sn.txt',(err,data)=>{
    if(err){
        console.log('defeat');
        return;
    }
    console.log(data.toString());  //如果是console.log(data) 会返回buffer
})
```
```javascript
//同步读取
let data = fs.readFileSync('./sn.txt');
console.log(data);
```
## 读取文件应用场景

- 电脑开机
- 程序运行
- 编辑器打开文件
- 查看图片
- 播放视频
- 播放音乐
- Git查看日志
- 上传文件
- 查看聊天记录
## 流式读取
```javascript
const rs = fs.createReadStream('./笑看风云.mp4');
rs.on('data',chunk=>{
  console.log(chunk.length);   //出现一块块字节  
})
//end  可选事件
rs.on('end',()=>{
  console.log('读取完成');
})
```
# 文件复制
```javascript
const fs = require('fs');

//方法a 流式操作复制文件
const rs = fs.createReadStream('./taytay.jpg');
const ws = fs.createWriteStream('./taytay1.jpg');

rs.on('data',chunk=>{
    ws.write(chunk);
})

//方法b readfile
let data = fs.readFileSync('./taytay.jpg');
fs.writeFileSync('./tat.jpg',data);


//
rs.pipe(ws);
```
当需要复制大文件时，使用流式操作方法比同步操作方法占用更少的内存。这是因为流式操作方法在处理文件时，通过分块读取和写入数据，而不是将整个文件加载到内存中。这样可以大大减少内存的使用量，特别是对于大型文件而言。
# 文件移动与重命名
```javascript
fs.rename('./s.txt','./a.txt',err=>{
  if(err){
    console.log('defeat');
    return;
  }
  console.log('success');
})    //可以改名也可以移动
```
# 文件删除
用fs.rm
# 文件夹操作
## 创建
```javascript
fs.mkdir('./hah',err=>{
    if(err){
        console.log('defeat');
        return;
    }
    console.log('success');
})

//递归创建
fs.mkdir('./a/b/c',{recursive:true},err=>{
    if(err){
        console.log('defeat');
        return;
    }
    console.log('success');
})

```
## 读取文件夹
```javascript
fs.readdir('./a',(err,data)=>{
  if(err){
    console.log('defeat');
    return;
  }
  console.log(data);
})
```
## 删除文件夹
```javascript
fs.rmdir('./html',err=>{
  if(err){
    console.log('defeat');
    return;
  }
  console.log('success');
})

//建议使用
fs.rm('./hah',recursive{true},err=>{
    if(err){
        console.log('defeat');
        return;
    }
    console.log('success');
})   //文件夹不是空 也会一起删
```
# 查看资源状态
```javascript
const fs = require('fs');

fs.stat('./tat.jpg',(err,data)=>{
    if(err){
        console.log('defeat');
        return;
    }
    console.log(data);
})
```
# 相对路径的bug
相对路径参照物：命令行的工作目录
__dirname  保存的是所在文件的所在目录的绝对路径  
所以一般可以这样写
```javascript
(__dirname + '/index.html');
```
