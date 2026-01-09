RN  —— AI对话记账

技术栈：

移动端：React Native (Expo)  状态管理：Zustand

后端 Nodejs Express Typescript 登陆注册 supabase auth JWT

对话功能实现 AI SDK  数据库 supabase Postgresql ORM：dirzzle

模型：deepseek



## 遇到的问题

1. 安卓调试的时候出问题 应该是安卓有些路径有中文的缘故？ 用ios设备就不会 

根据寻找资料 修改node_modules包即可 @expo的cli/build/src/start/server/metro/dev-server

/createMetroMiddleware.js 找到错误的地方 将metroConfig.projectRoot 包裹到new URL()

2.  const insets = useSafeAreaInsets()  //状态栏安全距离

3. 运用物理设备进行开发 不能用locolHost  用局域网ip地址
4. ’TextDecoderStream‘ doesn't exist    加一个polyfill解决

> 浏览器的种类和版本繁多，不同浏览器对 JavaScript 新特性的支持程度存在差异。例如，某些较新的浏览器支持像 `Promise`、`fetch` 这样的新特性，然而一些旧浏览器却不支持。要是你在代码里使用了这些新特性，在旧浏览器上运行时就会出现问题。
>
> 这时候，polyfill 就能发挥作用了。它是一段代码（通常是 JavaScript 代码），其作用是在不支持某个特性的浏览器中，模拟出该特性的功能。举例来说，`fetch` API 是用于发起网络请求的现代方式，老版本的 Internet Explorer 不支持它。你可以引入一个 `fetch` 的 polyfill，这个 polyfill 会检查浏览器是否支持 `fetch`，若不支持，它就会用旧的 `XMLHttpRequest` 来模拟 `fetch` 的功能，这样代码就能在旧浏览器上正常运行了。	
>
> ​	

5. 带花括号函数要return显示返回  没有花括号 或者是括号就是return那个数