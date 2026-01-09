# 概述
1. **是什么：**

vuex是一个vue的状态管理工具，状态就是数据
大白话：一个插件，帮助管理vue**通用**的数据（多组件共享的数据）

2. **场景：**
- 某个状态 在很多个组件来使用（个人信息）
- 多个组件共同维护一份数据（购物车）
3. **优势：**
- 共同维护一份数据，数据集中化管理
- 响应式变化
- 操作简洁（vuex提供了一些辅助函数）
# 创建一个空仓库
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691857393403-d66daddf-f913-4082-96f8-5f94b6d1e7c5.png#averageHue=%23dddbdb&clientId=u2c414616-6b34-4&from=paste&height=660&id=u05fb86b6&originHeight=841&originWidth=1826&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=502921&status=done&style=none&taskId=u7f13afd8-878a-4e46-b45a-d36c1589b8e&title=&width=1432.1568895257105)
# 核心概念 - state状态

1. 提供数据：

state提供唯一的公共数据源，所有共享的数据都要统一放到store中的state存储，类似于Vue中的data

2. 使用数据：
- 通过store直接访问

![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691897078252-2ddc96a8-4ca0-491d-b1ee-20091345fb84.png#averageHue=%234b4747&clientId=u14c0965b-b577-4&from=paste&height=318&id=VNTbD&originHeight=406&originWidth=724&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=92007&status=done&style=none&taskId=uea34bf9e-fc89-4039-9437-4404e80d570&title=&width=567.8431478732829)

- 通过辅助函数 

![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691900459187-1ced5f70-2528-4d1f-aa9a-6a3569ad89bb.png#averageHue=%23f3f2f2&clientId=u14c0965b-b577-4&from=paste&height=294&id=uc2bc770e&originHeight=375&originWidth=1431&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=230658&status=done&style=none&taskId=ud0503ec7-810c-4f34-b586-3775ef5b05b&title=&width=1122.3529621639057)
# mutations
vuex同样遵循单向数据流，组件中不能直接修改仓库的数据
this.$store.state.count++ （错误写法）  （但不会提示，除非通过strict:true 开启严格模式）
state数据的修改只能通过mutations

1. 定义mutations对象，对象中存放修改state的方法

![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691901305392-441edf53-18e8-43c8-9ee1-0ee0d39cd33c.png#averageHue=%2340403f&clientId=u14c0965b-b577-4&from=paste&height=413&id=u92c17319&originHeight=526&originWidth=786&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=189321&status=done&style=none&taskId=u501f5358-1c91-43f0-9ebd-0757bebeb78&title=&width=616.4705997629839)

2. 组件中提交调用mutations

 ![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691901347798-efd33ae0-5625-41e0-8eda-ee0ee844e332.png#averageHue=%239b9a99&clientId=u14c0965b-b577-4&from=paste&height=89&id=u11e282e8&originHeight=113&originWidth=669&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=42721&status=done&style=none&taskId=u0b487a29-6eee-42ba-87f4-41563f94301&title=&width=524.7058921646772)
## 传参
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691901414080-5ced1fba-a118-4f99-9c53-262ac301c5db.png#averageHue=%23aaaaaa&clientId=u14c0965b-b577-4&from=paste&height=495&id=u53350773&originHeight=631&originWidth=1049&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=212510&status=done&style=none&taskId=u5aa611c7-33cc-4480-861f-5798f7857e5&title=&width=822.745113424135)
注意点：mutation参数有且只能有一个，如果需要多个参数，则包装成一个对象
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691903930610-8da312cb-ca8c-4b43-99d2-38688163bfe3.png#averageHue=%23a4a3a3&clientId=u14c0965b-b577-4&from=paste&height=555&id=u775c9528&originHeight=708&originWidth=1848&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=357043&status=done&style=none&taskId=ua5f84043-0973-4619-ae43-8f2a30ff978&title=&width=1449.4117918091529)
# actions
可以处理异步操作
说明：mutations必须是同步的（便于监测数据变化，记录调试）
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691904104813-28a47fad-114f-4ac0-b04e-6b6b55f331d7.png#averageHue=%23637a87&clientId=u14c0965b-b577-4&from=paste&height=443&id=u61c79b14&originHeight=565&originWidth=1788&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=494299&status=done&style=none&taskId=ud5d89b7d-297a-49f5-ba2b-b87723e77de&title=&width=1402.3529673997648)
## actions的辅助函数
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691904186623-f925cbeb-05a9-49c8-8ffd-a76658ad25bb.png#averageHue=%23afacac&clientId=u14c0965b-b577-4&from=paste&height=627&id=u479f3225&originHeight=799&originWidth=1890&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=539893&status=done&style=none&taskId=u2c42b65f-d071-442d-9a83-f1e42396733&title=&width=1482.3529688957246)
# getters
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691904274076-82b99a60-1bcf-46b9-af3f-8b41fd2eb166.png#averageHue=%23a09f9f&clientId=u14c0965b-b577-4&from=paste&height=603&id=uf7a9d377&originHeight=769&originWidth=1856&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=561802&status=done&style=none&taskId=u688225f7-e24d-484e-92b4-9dcc2d28f5e&title=&width=1455.6863017304047)
# 模块module
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691904475300-624099a5-878c-456c-8c54-b4ab6c115a5f.png#averageHue=%23b0afaf&clientId=u14c0965b-b577-4&from=paste&height=630&id=ud97f82ac&originHeight=803&originWidth=1860&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=531898&status=done&style=none&taskId=u147bef7f-0284-428e-9b43-0b1c6af8d15&title=&width=1458.8235566910305)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1691905422093-203568f1-d328-4d81-bc75-9d38ec7c693c.png#averageHue=%23d3d0cf&clientId=u14c0965b-b577-4&from=paste&height=588&id=u9356af22&originHeight=750&originWidth=1691&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=480323&status=done&style=none&taskId=u85ae0cca-1f22-463d-9dcd-7f9d240ad76&title=&width=1326.2745346045874)
