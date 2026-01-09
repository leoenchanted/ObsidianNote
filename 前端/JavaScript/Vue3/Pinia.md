Pinia是Vue的最新状态管理工具，是Vuex的替代品
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697644655877-974c82e3-3028-4065-85b0-a4e78a8bcba9.png#averageHue=%23f0f0f0&clientId=ub6bc2fd8-1a50-4&from=paste&height=299&id=u4b197ab8&originHeight=381&originWidth=955&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=113614&status=done&style=none&taskId=u8c9071ab-4c2c-4537-b460-cdff52af160&title=&width=749.0196218494269)
## 创建
首先 npm install pinia
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697645264336-6b121457-8fca-4910-b258-604e2c18b46d.png#averageHue=%23f4f3f3&clientId=ub6bc2fd8-1a50-4&from=paste&height=333&id=u0d1124b9&originHeight=424&originWidth=604&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=148820&status=done&style=none&taskId=u273595ae-7158-459f-866d-0f4f8b4a746&title=&width=473.7254990545067)
## 定义store
```javascript
import { defineStore } from 'pinia'

// 你可以对 `defineStore()` 的返回值进行任意命名，但最好使用 store 的名字，同时以 `use` 开头且以 `Store` 结尾。(比如 `useUserStore`，`useCartStore`，`useProductStore`)
// 第一个参数是你的应用中 Store 的唯一 ID。
export const useAlertsStore = defineStore('alerts', {
  // 其他配置...
})
```
### setup store
在 _Setup Store_ 中：

- `ref()` 就是 `state` 属性
- `computed()` 就是 `getters`
- `function()` 就是 `actions`

pinia支持异步，直接写function就行。
## storeToRefs
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697733233694-3dc6cd15-c8b2-4b91-8b26-47986b121652.png#averageHue=%230f151f&clientId=u13e8aff9-fb49-4&from=paste&height=358&id=ub85080ee&originHeight=456&originWidth=794&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=44542&status=done&style=none&taskId=u45bbd9e8-8a1f-4738-b77a-bc8fd433e24&title=&width=622.7451096842357)
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1697733291343-25da0fa5-762f-4acf-9e62-2ab953b0cefc.png#averageHue=%23121924&clientId=u13e8aff9-fb49-4&from=paste&height=333&id=uf913fd9d&originHeight=495&originWidth=931&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=63761&status=done&style=none&taskId=uc2f45a45-c124-4242-b6bb-c223bf8affb&title=&width=627.1961059570312)
## Pinia持久化
