# 元素偏移量offset系列
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1675875729643-422a137d-a647-47cd-8d82-a8ee2a958cc1.png#averageHue=%23f3f6f3&clientId=u880c0e50-e29e-4&from=paste&height=526&id=u5b9f460d&originHeight=671&originWidth=1349&originalType=binary&ratio=1&rotation=0&showTitle=false&size=412567&status=done&style=none&taskId=u0edc5aac-e5bb-438d-bf17-d7f689e588a&title=&width=1058.0392354710755)
## offset和style的区别
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1675875838346-f008d8cd-1c4d-41dc-95fd-86b8bd1660b2.png#averageHue=%23f2f5f2&clientId=u880c0e50-e29e-4&from=paste&height=315&id=u3e683fcf&originHeight=401&originWidth=1585&originalType=binary&ratio=1&rotation=0&showTitle=false&size=233417&status=done&style=none&taskId=uc45887ff-2102-4375-bcde-c91a44dd9db&title=&width=1243.1372781480018)
# 元素可视区client系列
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1675922689768-9edc4a2a-4ee5-4cc9-bdba-7c2d2c0a54f5.png#averageHue=%23f4f7f4&clientId=ue260e5c7-94e8-4&from=paste&height=466&id=u9c72c6b0&originHeight=594&originWidth=1395&originalType=binary&ratio=1&rotation=0&showTitle=false&size=285685&status=done&style=none&taskId=u4629ec81-20d1-4962-ab4d-71eb6f67bb4&title=&width=1094.1176675182728)
width和height 不包含边框
## 立即执行函数

-  立即执行函数 (function(){})() 或者(function(){}())

立刻执行 不用调用  避免命名冲突问题
# 元素滚动scroll系列
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1675923097943-22661a30-bc10-46b3-a251-b9320cee7d06.png#averageHue=%23f5f8f5&clientId=ue260e5c7-94e8-4&from=paste&height=385&id=u0f092a1c&originHeight=491&originWidth=1338&originalType=binary&ratio=1&rotation=0&showTitle=false&size=271407&status=done&style=none&taskId=u7f4f8b0d-ccd4-4c2c-b995-138332203ba&title=&width=1049.4117843293543)
实际高度 如果内容超过边框 也可以包括
# mounseenter和mouseover区别
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1675923241880-9fe0ee20-e13d-41a1-9a68-e2833c625734.png#averageHue=%23f2f5f2&clientId=ue260e5c7-94e8-4&from=paste&height=319&id=u0af9fbe7&originHeight=407&originWidth=1339&originalType=binary&ratio=1&rotation=0&showTitle=false&size=152255&status=done&style=none&taskId=ucaec84b2-028b-4e8b-8b07-815b14bcd64&title=&width=1050.1960980695108)

# 动画函数封装
## 动画实现原理

- 核心原理：通过定时器setInterval()不断移动盒子位置

实验步骤：

1. 获得盒子当前位置
2. 让盒子在当前位置加上1个移动距离
3. 利用定时器不断重复这个操作
4. 加一个结束定时器的条件
5. 注意此元素需要添加定位，才能使用element.style.left
## 动画函数简单封装
注意函数传递2个参数，**动画对象**和**移动距离** 
```javascript
function animate(obj,target){
            var timer=setInterval(function(){
            if(obj.offsetLeft>=target){
                clearInterval(timer);
            }
            obj.style.left=obj.offsetLeft+1+'px';
        },30)
        }
```
## 动画函数给不同元素记录不同定时器

- 如果多个元素都使用这个动画函数，每次都要var声明定时器。我们可以给不同的元素使用不同的定时器（自己专门用自己的定时器）
- 核心原理： 利用JS是一门动态语言，可以很方便给当前对象添加属性（不用直接var来 直接添加属性？）
## 缓动效果原理
让元素运动速度有所变化，最常见的是让速度慢慢停下来
思路：

1. 让盒子每次移动的距离慢慢变小，速度就会慢慢落下来
2. 核心算法：（目标值-现在的位置）/10 作为每次移动的距离 步长
3. 停止的条件是：让当前的盒子位置等于目标位置就停止定时器
- **这样步长值容易出现小数，需要进行取整**  用Math.ceil()
## 动画函数添加回调函数
```javascript
function animiate(obj,target,callback){
  ......
  if(callback){
    callback();
  }
}


animate(span,800,function(){
  span.style.backgroundColor='red';
})
```
