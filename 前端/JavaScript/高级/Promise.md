## 如何使用Promise
### API
#### Promise构造函数:Promise(executor){}

- executor函数：执行器 (resolve,reject)=>{}
- resolve函数:内部定义成功时我们调用的函数 value=>{}
- reject函数:内部定义失败时我们调用的函数 reason=>{}

说明：executor会在Promise内部立即同步调用，异步操作在执行器中执行
#### Promise.prototype.then 方法：(onResolved,onRejected)=>{}
#### Promise.prototype.catch 方法：(onRejected)=>{}
#### Promise.resolve 方法：(value)=>{}
接受一个参数 作用是为了快速得到一个promise对象  返回一个成功/失败的promise对象
#### Promise.reject 方法 
返回一个失败的promise对象
#### Promise.all 方法：(promises)=>{}

- promises：包含n个promises的数组
- 返回一个新的promise，只有所有的promise都成功才成功，只要有一个失败了就直接失败
#### Promise.race 方法：promises)=>{}

- promises：包含n个promises的数组
- 返回一个新的promise，第一个完成的promise的结果状态就是最终的结果状态
