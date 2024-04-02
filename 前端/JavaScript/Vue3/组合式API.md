## setup选项
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697529207360-4d382ce4-501a-4b0a-8244-3cb7cc942270.png#averageHue=%23fefefe&clientId=u75f1b53b-6439-4&from=paste&height=514&id=uc6c097f9&originHeight=655&originWidth=949&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=128681&status=done&style=none&taskId=u847a7b73-2aa2-4410-b920-e689d99bbc0&title=&width=744.3137394084881)
setup比beforeCreate这个生命钩子还要早
### setup语法糖
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697529735223-9f32bec7-54ae-4650-a39b-ce429810f042.png#averageHue=%23537458&clientId=u75f1b53b-6439-4&from=paste&height=553&id=u30bc016b&originHeight=705&originWidth=1722&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=367122&status=done&style=none&taskId=ua298e894-631e-4bc3-abec-993beb7da53&title=&width=1350.588260549438)
原始如果要return的元素多了，很麻烦。因为要return了才能运用到template中。
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697531196955-fcb9af80-1e71-43a0-8148-5d2594ba5e9f.png#averageHue=%23f4f0f0&clientId=u75f1b53b-6439-4&from=paste&height=502&id=ud81d014b&originHeight=640&originWidth=820&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=246837&status=done&style=none&taskId=u13a1ba2e-a7a5-493f-8ed6-c01d985d4d5&title=&width=643.1372669283038)

## reactive和ref函数
### reactive()
接受一个对象类型的数据，返回一个响应式的对象
### ref()
接受简单类型或复杂类型的 数据，返回一个响应式对象
本质：是在原有传入数据的基础上，外层包了一层对象，包成了复杂类型。之后再借助reactive实现的响应式。
注意点：

1. 脚本中访问数据用过.value
2. template中，.value不需要加

![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697531774271-0cebfa63-d575-44a2-a32f-844c12e7fd56.png#averageHue=%2320201f&clientId=u75f1b53b-6439-4&from=paste&height=346&id=u07b11710&originHeight=441&originWidth=730&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=171513&status=done&style=none&taskId=u06e636d7-039f-461a-9647-10d18db1dc7&title=&width=572.5490303142217)
### ref()

接受简单类型或复杂类型的 数据，返回一个响应式对象

==本质：==是在原有传入数据的基础上，外层包了一层对象，包成了复杂类型。之后再借助reactive实现的响应式。

==注意点：==

1. 脚本中访问数据用过.value
2. template中，.value不需要加

![](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697531774271-0cebfa63-d575-44a2-a32f-844c12e7fd56.png)

### toRefs()

将 reactive 或 ref 对象的属性传递给非响应式上下文（如函数、回调或非 Vue 组件的模板）非常有用。

当你从 reactive 对象中解构出属性时，这些属性默认不是响应式的。如果你需要在模板之外的地方访问这些属性，并且希望它们保持响应性，那么你需要使用 toRefs 来转换这些属性。

#### 功能

- **创建响应式引用**：toRefs 接受一个响应式对象，并返回一个新对象，新对象的每个属性都是一个响应式引用，即 ref 对象。
- **保持响应性**：使用 toRefs 转换后的响应式引用可以在非响应式上下文中使用，同时保持其响应性。
- **避免响应式属性丢失**：在某些情况下，如将响应式对象作为函数参数传递时，直接解构的属性可能会丢失响应性。toRefs 可以确保即使在这种情况下，属性也保持响应性。
### 总结
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697531799947-39f3f0a2-b89e-4dc2-92a7-26061d23097f.png#averageHue=%23f6f2f2&clientId=u75f1b53b-6439-4&from=paste&height=518&id=ueeeaa828&originHeight=661&originWidth=1040&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=289090&status=done&style=none&taskId=u9985148c-aac1-40f8-a52c-ae920dc37ee&title=&width=815.6862897627268)
## computed
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697531846544-a4d9dbc2-5bf2-4395-b4cf-a8fd3e6b0a6d.png#averageHue=%23c7c2b3&clientId=u75f1b53b-6439-4&from=paste&height=478&id=uc7601a04&originHeight=610&originWidth=1461&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=348727&status=done&style=none&taskId=ub83452f3-bcfc-460f-9f8b-6243b169e15&title=&width=1145.8823743685998)
## watch
侦听一个或者多个数据的变化，数据变化时执行回调函数。
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697533701060-938860a3-710f-4eda-9783-2c4f20acaa9f.png#averageHue=%23527260&clientId=u75f1b53b-6439-4&from=paste&height=651&id=ucaf3b502&originHeight=830&originWidth=1229&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=441324&status=done&style=none&taskId=u9bc2f806-c706-434b-82f6-37544bec416&title=&width=963.9215866522992)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697533682003-9988e426-89a5-4d4f-8f42-5cda96acbe87.png#averageHue=%23455f56&clientId=u75f1b53b-6439-4&from=paste&height=609&id=u921d122e&originHeight=776&originWidth=1256&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=447963&status=done&style=none&taskId=ucc1f9518-b3ae-4876-b65a-2f3ee0c097d&title=&width=985.0980576365239)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697535068630-d9166d6d-d954-44ae-95ac-3973ea9745cf.png#averageHue=%231e1e1e&clientId=u75f1b53b-6439-4&from=paste&height=331&id=u16b68f61&originHeight=422&originWidth=822&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=270002&status=done&style=none&taskId=ue36105a5-518b-4eb5-812f-b469c126025&title=&width=644.7058944086167)
监视的是ref对象
### immediate
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697535551088-a5c960d1-aa0f-4d7f-82e6-1dbb666c89eb.png#averageHue=%23768c72&clientId=u75f1b53b-6439-4&from=paste&height=607&id=u6df18456&originHeight=774&originWidth=1236&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=302686&status=done&style=none&taskId=ucdd42c2b-dcd2-4624-bb2e-db3ff717996&title=&width=969.4117828333945)
### deep深度监视
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697535344824-2a040bfe-031d-47f2-bab9-d2875c9a39fd.png#averageHue=%232c3126&clientId=u75f1b53b-6439-4&from=paste&height=100&id=uf05fc73b&originHeight=127&originWidth=835&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=139597&status=done&style=none&taskId=ud88b3aaf-d529-489b-bcfe-0a9f4a2cdb7&title=&width=654.9019730306508)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697535440946-ce6d3f6f-33bd-4ea7-8aa6-1cb7324024fe.png#averageHue=%23241f1e&clientId=u75f1b53b-6439-4&from=paste&height=377&id=u884fde2a&originHeight=481&originWidth=817&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=251570&status=done&style=none&taskId=uc24d64cd-3184-42b4-a67a-e02e2ce94a9&title=&width=640.7843257078343)
### 对于对象中的属性的监视
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697535497153-c812cc11-2b0d-43a1-a6c4-2a0fc85ff39c.png#averageHue=%23313228&clientId=u75f1b53b-6439-4&from=paste&height=137&id=u7989e4c2&originHeight=175&originWidth=839&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=128944&status=done&style=none&taskId=u9cab72c7-f9dd-40c7-b8d2-968961b7629&title=&width=658.0392279912767)
这个不需要deep就能看到对象中的属性
### 总结
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697535525274-39266b33-b31d-4cdd-a9cb-376997c03a13.png#averageHue=%23f4f1f1&clientId=u75f1b53b-6439-4&from=paste&height=613&id=u1e0309d4&originHeight=781&originWidth=1235&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=315091&status=done&style=none&taskId=u4ca51144-72c5-4066-a3c1-2b146fe5c69&title=&width=968.627469093238)
## 生命周期函数
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697539782862-9c6c514f-6d53-43ed-8a99-ea412eac1fef.png#averageHue=%23f1f6f8&clientId=ub501b6a3-ce0d-4&from=paste&height=636&id=u1a4ea6e4&originHeight=811&originWidth=1511&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=462781&status=done&style=none&taskId=u85da561b-f61d-41a2-b089-0a3fdb5c3d2&title=&width=1185.0980613764232)
之前Vue2在beforeCreate和created的相关代码一律放在setup中执行
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697539925775-6b1ca7dc-3076-491b-b04a-8c767b197a20.png#averageHue=%2324211f&clientId=ub501b6a3-ce0d-4&from=paste&height=270&id=u7d6cc329&originHeight=344&originWidth=905&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=237636&status=done&style=none&taskId=u7667643e-6ec7-4d9a-8888-c991ee19837&title=&width=709.8039348416036)
## 父子通信
### 父传子
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697540039434-dd0e9ad8-81fa-4367-866a-7c3553092ada.png#averageHue=%236b8b78&clientId=ub501b6a3-ce0d-4&from=paste&height=549&id=u305c5ca4&originHeight=700&originWidth=1799&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=446667&status=done&style=none&taskId=ubaa6d9e7-44d1-4165-9b7b-565c90fec2f&title=&width=1410.980418541486)
局部组件，导入进来就能用
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697540121127-da9c5336-753d-4041-9c9e-4f42ffaf8471.png#averageHue=%231f1e1e&clientId=ub501b6a3-ce0d-4&from=paste&height=437&id=u47ac65c2&originHeight=557&originWidth=784&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=224058&status=done&style=none&taskId=u12826e3e-a018-4792-b19d-3fa8f86be71&title=&width=614.901972282671)

![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697540186159-deeee1ef-b5e5-4240-ab5c-52a8bf8271c9.png#averageHue=%23221f1e&clientId=ub501b6a3-ce0d-4&from=paste&height=351&id=u91c28ca5&originHeight=447&originWidth=835&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=263408&status=done&style=none&taskId=uf60e9a5a-a41d-4feb-b1ee-83e3b7f31d6&title=&width=654.9019730306508)
### 子传父
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697540256193-f6ad2cf4-d7c8-41f6-88e8-fb85c228c126.png#averageHue=%23547a68&clientId=ub501b6a3-ce0d-4&from=paste&height=589&id=u83e33007&originHeight=751&originWidth=1745&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=586540&status=done&style=none&taskId=u3da2ff0a-4cab-4c30-825f-af9168c1bb7&title=&width=1368.6274765730368)
## 模板引用
通过ref标识获取真实的dom对象或者组件实例对象
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697540505506-c55a07bc-1112-4f88-9614-09b7faafbabf.png#averageHue=%237c7c62&clientId=ub501b6a3-ce0d-4&from=paste&height=525&id=uf7af9a3b&originHeight=669&originWidth=1482&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=324877&status=done&style=none&taskId=ue8afc3a5-5ae1-4bbe-bf39-4f94f1cab04&title=&width=1162.3529629118857)
### defineExpose()
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697540600099-274607e9-05ee-484c-9682-adbf7e264c19.png#averageHue=%23f5f3f2&clientId=ub501b6a3-ce0d-4&from=paste&height=551&id=u55a795c3&originHeight=702&originWidth=1512&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=284152&status=done&style=none&taskId=ue928809b-0726-4466-bd5c-18f60d95b06&title=&width=1185.8823751165796)
### 总结
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697540616935-8a127937-59d8-4ccc-a99e-f3ff4c0ee0eb.png#averageHue=%23f5f2f2&clientId=ub501b6a3-ce0d-4&from=paste&height=353&id=u68bf2ba4&originHeight=450&originWidth=761&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=115389&status=done&style=none&taskId=u86f138f4-4cd1-4df0-9a24-02ffc467973&title=&width=596.8627562590722)
## provide和inject
### 跨层传递普通数据
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697560021030-0d36a421-46ec-4ad1-ab7d-42f9928eaedb.png#averageHue=%23aca079&clientId=ub501b6a3-ce0d-4&from=paste&height=548&id=ua43f99ca&originHeight=699&originWidth=1259&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=294835&status=done&style=none&taskId=ub29d1279-bcf7-4ac0-8b4f-cc2c1d6a1f3&title=&width=987.4509988569932)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697560494591-831bb2cc-b360-4c01-a792-e700e663a202.png#averageHue=%23aca58c&clientId=ub501b6a3-ce0d-4&from=paste&height=539&id=uf475bf73&originHeight=687&originWidth=1714&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=306267&status=done&style=none&taskId=ubcd5c4ce-a5d0-44e9-8ebe-bbda7b9964b&title=&width=1344.3137506281862)
