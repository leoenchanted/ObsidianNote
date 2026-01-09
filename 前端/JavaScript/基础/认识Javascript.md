# Javascript是什么
是一种运行在客户端的脚本语言（script是脚本的意思）
脚本语言：不需要编译，运行过程中由js解释器逐行来解释并执行
# js的作用

- 表单动态校验（密码强度检测）（js产生最初的目的）
- 网页特效
- 服务端开发（Node.js）
- 桌面程序
- APP
- 控制硬件-物联网
- 游戏开发
# js的组成
![image.png](https://cdn.nlark.com/yuque/0/2022/png/33778458/1671950983000-f344326f-81ed-4001-99de-92f092e2753b.png#averageHue=%23fafdfa&clientId=u08ea9f63-a54b-4&from=paste&height=256&id=ucd9bda9e&originHeight=215&originWidth=520&originalType=binary&ratio=1&rotation=0&showTitle=false&size=26215&status=done&style=none&taskId=u33b61c08-c039-446a-a9e6-91cd9aaedf9&title=&width=618.8431396484375)
# js初体验
## 行内式js
写在HTML那里
```css
<input type="button" vaule="点我试试" onclick="alert('Hello Worrld')"/>
```

- HTML中用双引号，js中用单引号
- 可读性差，不方便阅读
- 引号易错，引导多层嵌套匹配时，非常容易弄混
- 特殊情况下使用
## 内嵌js
```javascript
<script>
  alert('Hello World');
</script>
```

- 学习时常用方法
- 将多行js代码写到标签中
## 外部js
```javascript
<script src="my.js"></script>
```

- 利于结构化，美观，方便文件级别复用
- 标签中间不可写代码
- 适用js码量大的时候
# js的输入和输出

- alert（）  浏览器弹出警示框
- console.log（） 浏览请控制台打印输出信息
- prompt（）   弹出输入框，用户可输入
