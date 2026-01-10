模块暴露数据
用module.exports 可以暴露任何数据
```javascript
// shabi.js
function ab {
console.log('hehe');
}
module.exports = ab;
//another.js
const ab = require('./shabi.js');
ab();   //hehe



//or shabi.js
function ab{};
function ac{};
module.exports = {
  ab,
  ac
}
//another.js
const shabi = require('./shabi.js');
shabi.ab();
shabi.ac();
```
exports = vaule  不能直接用   除非exports.shabi = shabi; 相当于添加对象进去 因为mdoule.exports = exports = {}   而另一边require是导进mdoule.exports 的
# 导入
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1689575831464-cee9665e-fee4-4b17-8f2e-24d3c956ed54.png#averageHue=%23fcfbfb&clientId=u8f7d8580-d3fe-4&from=paste&height=432&id=u2b15ee61&originHeight=551&originWidth=1118&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=283496&status=done&style=none&taskId=u6bdf4b26-8e6a-4c6d-b790-755119000a9&title=&width=876.8627614949313)
