此处编写的就是Vue组件实例的配置项，通过一定语法，直接混入到组件内
注意点：如果此处和组件内，提供了同名的data或methods，则组件内优先级更高
如果编写生命周期函数，则mixins中的生命周期函数和页面的生命周期函数会有数组管理，统一执行
