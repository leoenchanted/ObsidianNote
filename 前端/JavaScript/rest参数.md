# rest参数
用于获取函数多余的参数
形式：`(...变量名)` 把一个分离的参数序列整合为一个数组，值是一个数组。
```javascript
function Test(...num){
  let res = 0;
  for(let i=0;i<num.length;i++){
    res+=num[i];
  }
  return res;
}
console.log(Test(1,2))  //输出3
console.log(Test(2,3,4,5)) //输出14
```
