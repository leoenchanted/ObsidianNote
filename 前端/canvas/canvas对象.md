<a name="CURFg"></a>
## canvas对象常用的属性
| 属性 | 说明 |
| --- | --- |
| width | canvas对象的宽度 |
| height | canvas对象的高度 |

<a name="hFdHO"></a>
## canvas的常用对象方法
| 属性 | 说明 |
| --- | --- |
| getContext("2d") | 获取canvas 2D上下文环境对象 |
| toDataURL() | 获取canvas对象产生的位图的字符串 |

toDataURL()有以下两个用处：

- 发送图片数据到Web服务器的数据库，进行长期保存。
- 在浏览器中直接打开，进行本地保存。

对于在浏览器中打开并进行本地保存，我们一般使用以下方法：<br />`window.location=cxt.toDataURL("image/png");`
<a name="xQJMn"></a>
## globalAlpha属性
语法：<br />`cxt.globalAlpha=数值;`<br />用这个属性来定义canvas环境的透明度。
<a name="akGoo"></a>
## globalCompositeOperation属性
语法：<br />`cxt.globalCompositeOperation=属性值;`<br />![](https://cdn.nlark.com/yuque/0/2023/jpeg/anonymous/1699343285571-bc1a0afe-539d-4703-a1fa-5b0e8453ea76.jpeg#averageHue=%239c948a&id=Bm1d9&originHeight=3527&originWidth=2839&originalType=binary&ratio=1&rotation=0&showTitle=false&status=done&style=none&title=)

