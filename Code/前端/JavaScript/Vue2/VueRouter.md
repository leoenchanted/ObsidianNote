# VueRouter的使用
## 5个基础步骤
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691805559119-909694e2-a54b-485c-83dd-7db2958a7f7f.png#averageHue=%23a6a6a5&clientId=ud8ecb1a5-d212-4&from=paste&height=666&id=u981bcd7d&originHeight=849&originWidth=1069&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=308466&status=done&style=none&taskId=u16c9cb75-603c-42c4-8fc3-b8b09026f1e&title=&width=838.4313882272643)
## 2个核心步骤
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691805862104-f1ea369f-b39c-4902-909a-1b22c268895f.png#averageHue=%23b6b2b1&clientId=ud8ecb1a5-d212-4&from=paste&height=597&id=u0ac84c99&originHeight=761&originWidth=1791&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=604585&status=done&style=none&taskId=u31c44085-3a21-4380-86d3-1e5b1943fdc&title=&width=1404.7059086202344)
# 组件存放问题
为什么路由相关的组件要放在views目录呢
## 组件分类
.vue文件分2类； 页面组件&复用组件
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691806444218-1454c641-1b59-4815-b570-17cf3450fe8c.png#averageHue=%23f1eded&clientId=ud8ecb1a5-d212-4&from=paste&height=203&id=u94ecc32e&originHeight=259&originWidth=664&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=82351&status=done&style=none&taskId=ud10bd980-122d-45c1-a896-d54bfa70f5f&title=&width=520.7843234638948)
# 路由的封装抽离
问题：所有的路由配置都堆在main.js中吗
这样以后项目大了 这里会越堆越大   
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691807342854-510befe3-a24e-4a3e-8446-8ac0444196f6.png#averageHue=%23a2a09f&clientId=ud8ecb1a5-d212-4&from=paste&height=467&id=u670885c3&originHeight=595&originWidth=1811&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=550058&status=done&style=none&taskId=u30ada69f-2809-48ce-b4fb-5ac70bf48c6&title=&width=1420.3921834233636)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691807493175-7769bd8b-5cbc-4416-b2e3-dd930522c77f.png#averageHue=%23f6f5f5&clientId=ud8ecb1a5-d212-4&from=paste&height=157&id=u9c7ef10b&originHeight=200&originWidth=1043&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=60656&status=done&style=none&taskId=u8f156d89-7e03-4d74-af55-c88f957e87c&title=&width=818.0392309831961)
# router-link
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691807764181-5c3a7db8-951e-4f7e-8bd3-b518b9917bbc.png#averageHue=%23f5f4f4&clientId=ud8ecb1a5-d212-4&from=paste&height=567&id=uf2900762&originHeight=723&originWidth=984&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=182958&status=done&style=none&taskId=ua0c6f81e-ada6-4577-8e42-8700f6319f9&title=&width=771.7647203139645)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691807776792-000a864a-f899-4224-a5a4-2ad3c4fd185e.png#averageHue=%23b6b7b5&clientId=ud8ecb1a5-d212-4&from=paste&height=545&id=uf5ae5073&originHeight=695&originWidth=1740&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=527310&status=done&style=none&taskId=u0083655d-8d8d-452e-924a-27a78f18c92&title=&width=1364.7059078722543)
## 声明式导航 - 两个类名
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691809369275-79ac0650-4dd0-4d4b-bc35-26a77526945b.png#averageHue=%23e4e2e1&clientId=ud8ecb1a5-d212-4&from=paste&height=620&id=u3df2ae16&originHeight=790&originWidth=1900&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=645871&status=done&style=none&taskId=u1846120e-3b9c-4a6c-8de2-c2078143054&title=&width=1490.1961062972894)
# 跳转传参
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691815844849-f6109fdb-258c-4875-8d1e-63799fee9b13.png#averageHue=%23faf6f6&clientId=ud8ecb1a5-d212-4&from=paste&height=554&id=u26930eb8&originHeight=706&originWidth=963&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=272394&status=done&style=none&taskId=u19b0b8e6-6b3b-4598-915b-544b1410b54&title=&width=755.2941317706787)
## 查询传参
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697338442964-4b6c42cc-5b4c-4c99-838c-3f51ce1889cc.png#averageHue=%23949191&clientId=u3e08998d-7267-4&from=paste&height=719&id=u67781e1f&originHeight=917&originWidth=1851&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=722012&status=done&style=none&taskId=u3b0b83f1-adf7-4e46-9caf-dd125ce4d80&title=&width=1451.7647330296224)
## 动态路由传参
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697338637430-6aacd32f-e186-45cd-9b51-dded2037444b.png#averageHue=%23898484&clientId=u3e08998d-7267-4&from=paste&height=417&id=u6477e9ca&originHeight=532&originWidth=952&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=291775&status=done&style=none&taskId=uc7c5c5a8-057a-4f94-a1c1-3cc81eb067e&title=&width=746.6666806289576)
# 重定向
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691815953817-d3089025-0ad2-4a33-932a-5fd44470d9d2.png#averageHue=%23dcd9cb&clientId=ud8ecb1a5-d212-4&from=paste&height=616&id=udd891a65&originHeight=785&originWidth=1813&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=504867&status=done&style=none&taskId=ubfb9fd9a-6107-4662-a4d5-77b614d0133&title=&width=1421.9608109036765)
后面是空白的时候 ，也就是默认的时候，跳转到redirect的地方
当找不到路径时候
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691816240468-d977a6f6-f4a6-4763-87c6-a668fc0ab006.png#averageHue=%23c2c1c1&clientId=ud8ecb1a5-d212-4&from=paste&height=499&id=u3dd25bd6&originHeight=636&originWidth=1705&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=413366&status=done&style=none&taskId=ude69a1e1-15e4-4376-9d41-0b30e599529&title=&width=1337.254926966778)
## 模式设置
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691816288324-d51f3b15-61d9-4685-a29a-089d758af1c3.png#averageHue=%23dbd8d8&clientId=ud8ecb1a5-d212-4&from=paste&height=518&id=aD3pS&originHeight=661&originWidth=1648&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=316089&status=done&style=none&taskId=ua416535f-cbd1-4d7c-924e-7382d732a22&title=&width=1292.5490437778594)
# 两种路由跳转方式
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691816658160-5077a900-5551-4660-b47e-4d7e36213601.png#averageHue=%23b0b0af&clientId=ud8ecb1a5-d212-4&from=paste&height=569&id=ua8c1f05c&originHeight=726&originWidth=906&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=243410&status=done&style=none&taskId=ud66418ea-ba0a-4a02-9ed4-e9996c8dcd0&title=&width=710.58824858176)
## 跳转参数
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691817223442-cd909580-04da-4110-aee5-2bbece2567ce.png#averageHue=%239f9d9d&clientId=ud8ecb1a5-d212-4&from=paste&height=675&id=ua332f844&originHeight=861&originWidth=785&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=308220&status=done&style=none&taskId=u76b19cfd-bb20-4648-a181-8a3a36f6314&title=&width=615.6862860228274)
# 路由出口
<router-view></router-view>
# 面经案例
嵌套路由配置（二级路由）：
children
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691823129825-4160b1fe-30d9-4a48-8863-4e3357602dc9.png#averageHue=%23282d35&clientId=u5264cacf-ac9b-4&from=paste&height=313&id=ufe324837&originHeight=399&originWidth=386&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=17205&status=done&style=none&taskId=u136d2175-1de3-4431-9080-2cc660c7c82&title=&width=302.74510370039667)
动态理由传参：
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691822406457-12f2dc57-de8e-4835-985d-a8365cfe30c1.png#averageHue=%232a2e37&clientId=u5264cacf-ac9b-4&from=paste&height=87&id=ud3a414a6&originHeight=111&originWidth=375&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=4956&status=done&style=none&taskId=udaf07808-d72a-49d6-9bef-f014243a752&title=&width=294.1176525586755)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691822471140-ebe0f78a-aafd-450b-ac0a-fd5ae08682d8.png#averageHue=%232b303a&clientId=u5264cacf-ac9b-4&from=paste&height=60&id=u50ab3caa&originHeight=76&originWidth=535&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=6639&status=done&style=none&taskId=u93e8aade-b6c8-4e1e-a2c2-236e8c320ed&title=&width=419.6078509837104)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691822351605-9f453c63-d7e8-45ba-9aed-1ad202dfdd94.png#averageHue=%232a2e37&clientId=u5264cacf-ac9b-4&from=paste&height=138&id=uea82eb23&originHeight=176&originWidth=908&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=21477&status=done&style=none&taskId=u985c09d9-fa40-470f-9501-2ede01f1574&title=&width=712.156876062073)
## 组件缓存keep-alive
面经点到详情页，又点返回，数据重新加载  → 希望回到原来浏览的位置
原因：路由跳转后，组件被销毁了，返回回来组件又被重建，所以数据重新加载

1. **keep-alive是什么**

是Vue的内置组件，当它包裹动态组件时，会缓存不活动的组件实例，而不是销毁它们

2. **优点**

在组件切换过程中把切换出去的组件保留在内存中，防止重复渲染DOM，减少加载时间和性能消耗

3. **三个属性（了解）**
- include：组件名数组，只有匹配的组件会被缓存
- exclude：组件名数组，任何匹配的组件都不会被缓存
- max：最多可以缓存多少组件实例

![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697339208134-0fe3dfe3-9ab5-40ca-91a4-b5eebaf77bea.png#averageHue=%23261f1e&clientId=u3e08998d-7267-4&from=paste&height=605&id=u64e6278f&originHeight=771&originWidth=746&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=352446&status=done&style=none&taskId=ude4a7104-0197-4f24-8ce0-04c1cba4b33&title=&width=585.0980501567252)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697339320958-4d4e0d04-5545-475d-97c8-9483548022c1.png#averageHue=%232c2f27&clientId=u3e08998d-7267-4&from=paste&height=122&id=u9d40a98d&originHeight=155&originWidth=685&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=123489&status=done&style=none&taskId=uad3d4c7b-edf4-488f-a47f-e274ddaa091&title=&width=537.2549120071806)

4. **这个使用会触发两个生命周期函数（了解）**

![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697338876731-abe94515-93e9-452a-aed6-57152bb777b8.png#averageHue=%23e8e6e5&clientId=u3e08998d-7267-4&from=paste&height=110&id=u55706f84&originHeight=140&originWidth=950&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=93764&status=done&style=none&taskId=u5a968267-ee94-481f-8914-caa6d5c9981&title=&width=745.0980531486447)
# 路由导航守卫
```javascript
router.beforeEach((to,from,next)=>{
  //1.to  往哪里去，到哪去的路由信息对象
  //2.from  从哪里来，从哪来的路由信息对象
  //3. next()是否放行  next(路径)拦截到某个路径页面
})
```
# 方法属性
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1692547644718-290efb44-89a6-4e26-8109-5d254429a21b.png#averageHue=%23fefefe&clientId=u209fa4b7-cb72-4&from=paste&height=200&id=u09f44858&originHeight=255&originWidth=554&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=30391&status=done&style=none&taskId=u940e5c25-7424-411b-ac82-444e60b870e&title=&width=434.5098120466833)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1692547657772-44da138e-58a6-4da7-8376-53e526e7cfb1.png#averageHue=%23fefefe&clientId=u209fa4b7-cb72-4&from=paste&height=397&id=ubc3cee74&originHeight=506&originWidth=556&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=70269&status=done&style=none&taskId=u76ce78af-5058-47fd-9b1e-8fdc657638f&title=&width=436.07843952699625)
