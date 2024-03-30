**
localStorage** 是 Web 浏览器提供的一个用于在浏览器端保存键值对数据的API。它可以让开发者在用户的本地浏览器上持久化存储一些数据，以便在同一域名下的页面间进行数据传递和共享。数据存储在 **localStorage** 中通常不会过期，除非被主动清除或者用户手动清除浏览器数据。

请注意，localStorage 中存储的数据都是以字符串的形式进行存储的。如果需要存储对象或其他非字符串类型的数据，需要先将其转换成字符串再进行存储，反之亦然。
## 存储数据
```javascript
// 将数据存储到localStorage中
localStorage.setItem('key', 'value');

```
## 获取数据
```javascript
// 从localStorage中获取数据
const data = localStorage.getItem('key');

```
## 移除数据
```javascript
// 从localStorage中移除指定键的数据
localStorage.removeItem('key');

```
## 清空所有数据
```javascript
// 清空localStorage中的所有数据
localStorage.clear();

```


