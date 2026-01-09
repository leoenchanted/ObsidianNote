# 传统布局与flex布局
## 传统布局

- 兼容性好
- 布局繁琐
- 局限性，不能在移动端很好的布局
## flex弹性布局

- 操作方便，布局即为简单，移动端应用很广泛
- PC端浏览器支持情况较差
- IE 11或更低版本，不支持或仅部分支持

建议：

1. 在PC端还是~~传统布局~~    新增： 现在PC端也几乎已经完全普及及使用，只有非常少数的网站依然在用浮动来布局；  
2. 移动端或者不考虑兼容性的PC端页面布局，使用flex弹性布局
# 布局原理
flexible box， 弹性布局，任何一个容器都可以指定flex布局

- 为父盒子设为flex布局以后，子元素的float、clear和vertical-align失效
- 采用flex布局的元素简称容器，其所有子元素称为flex项目
- 通过给父盒子添加flex属性，控制子盒子的位置和排列方式

---

# 父项常见属性
## flex-direction设置主轴方向
![1.png](https://cdn.nlark.com/yuque/0/2022/png/33778458/1671210391566-2edfdd45-d4ab-4be0-84f3-8fe380118bfc.png#averageHue=%23f8fbf8&clientId=ub74c2589-ad4f-4&from=drop&id=u905789c2&originHeight=706&originWidth=1421&originalType=binary&ratio=1&rotation=0&showTitle=false&size=114587&status=done&style=none&taskId=u89d31274-9688-4516-9c04-abac2f3f7d0&title=)
### 属性值
该属性决定主轴方向 （即项目的排列方向）
注意：主轴和侧轴是会变化的，看fd设置谁为主轴，剩下就是侧轴。子元素跟着主轴来排列

| 属性值 | 说明 |
| --- | --- |
| row | 默认值从左到右 |
| row-reverse | 从右到左 |
| column  | 从上到下 |
| column-reverse | 从下到上 |

## justify-content 设置主轴上的子元素排列方式
定义了项目在主轴上的对齐方式
注意：使用这个属性之前一定要确定好主轴是哪个

| 属性值 | 说明 |
| --- | --- |
| flex-start | 默认值 从头部开始 如果主轴是x轴，则从左到右 |
| flex-end | 从尾部开始排列 |
| center | 在主轴居中对齐（如果主轴是x轴则水平居中） |
| space-around | 平分剩余空间 |
| space-between | 先两边贴边 再平分剩余空间  **（重要）** |

## flex-wrap 设置子元素是否换行
默认是不换行的

| 属性值 | 说明 |
| --- | --- |
| nowrap | 默认值，不换行 |
| wrap | 换行    多行 |

## align-items 设置侧轴上的子元素排列方式（单行） 
该属性是控制子项在侧轴（默认y轴）上的排列方式 在子项为单项的时候使用

| 属性值 | 说明 |
| --- | --- |
| flex-start  | 默认值，从上到下 |
| flex-end | 从下到上 |
| center | 垂直居中 |
| stretch | 拉伸 |

## align-content 设置侧轴上的子元素的排列方式（多行）
| 属性值 | 说明 |
| --- | --- |
| flex-start |  在侧轴的头部开始排列 |
| flex-end | 在侧轴的尾部开始排列 |
| center | 在侧轴中间显示 |
| space-around | 子项在侧轴平分剩余空间 |
| space-between | 子项在侧轴先分布两头，在平分剩余空间 |
| stretch | 默认值，设置子项元素高度平分父元素高度 |

## flex-flow

- **是flex-direction和flex-wrap属性的复合属性**
```css
flex-flow: row wrap ;
```
# 子项常见属性
## flex-grow 长大

- 在容器主轴上存在剩余空间时，`flex-grow`才有意义
- 该属性的值，称为**放大因子**，常见的属性值如下：
| 属性值 | 说明 |
| --- | --- |
| 0 默认值 | 不放大，保持初始值 |
| initial | 设置默认值，与0等效 |
| n | 放大因子：正数 |

## flex-shrink 缩小

- 当容器主轴“空间不足”且“禁止换行”时，`flex-shrink`才有意义
- 该属性的值，称为**收缩因子**，常见的属性值如下：
| 属性值 | 说明 |
| --- | --- |
| 1 默认值 | 允许项目收缩 |
| initial | 设置默认值，与1等效 |
| 0 | 禁止收缩，保持原始尺寸 |
| n | 收缩因子：正数 |

## align-self 覆盖container align-items属性

- 该属性可以覆盖容器的`align-items`，用以自定义某个项目的对齐方式
| 属性值 | 说明 |
| --- | --- |
| auto 默认值 | 继承`align-items`属性 |
| flex-start | 与交叉轴起始线对齐 |
| flex-end | 与交叉轴终止线对齐 |
| center | 与交叉轴中间线对齐：居中对齐 |
| stretch | 在交叉轴方向上拉伸 |
| baseline | 与基线对齐 |

## order 排序
 **order 决定了 flex items 的排布顺序 **

-  可以设置任意整数（正整数、负整数、0），值越小就越排在前面 
-  默认值是 0
## flex-basis
属性定义了在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小。

- auto（默认值）、具体的宽度数值（100px）
## flex属性

- **flex 是 flex-grow || flex-shrink || flex-basis 的简写,flex 属性可以指定1个，2个或3个值。 **

◼**单值语法: 值必须为以下其中之一: **
◻ 一个无单位数(<number>): 它会被当作<flex-grow>的值。 
◻ 一个有效的宽度(width)值: 它会被当作 <flex-basis>的值。 
◻ 关键字none，auto或initial. 
◼ **双值语法: 第一个值必须为一个无单位数，并且它会被当作 <flex-grow> 的值。 **
◻ 第二个值必须为以下之一： 
✓ 一个无单位数：它会被当作 <flex-shrink> 的值。 
✓ 一个有效的宽度值: 它会被当作 <flex-basis> 的值。 
◼ **三值语法: **
◻ 第一个值必须为一个无单位数，并且它会被当作 <flex-grow> 的值。 
◻ 第二个值必须为一个无单位数，并且它会被当作 <flex-shrink> 的值。 
◻ 第三个值必须为一个有效的宽度值， 并且它会被当作 <flex-basis> 的值。
