在JavaScript中，扩展运算符由三个连续的点...表示
# 用途

## 1.函数调用
```javascript
function sum(x, y, z) {
    return x + y + z;
}
const numbers = [1, 2, 3];
console.log(sum(...numbers)); // 输出: 6
```
## 2.数组字面量
```javascript
const parts = ['shoulders', 'knees'];
const body = ['head', ...parts, 'and', 'toes'];
// body 现在是 ['head', 'shoulders', 'knees', 'and', 'toes']
```
