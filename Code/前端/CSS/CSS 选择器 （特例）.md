# 大于符号选择器
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1688403603093-f1ba70cb-d3de-402e-94a9-8d4fb51e14ec.png#averageHue=%23f0e7be&clientId=u19314100-b26f-4&from=paste&height=654&id=u6669ba0e&originHeight=834&originWidth=1873&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=367956&status=done&style=none&taskId=u7da66cf3-093f-4d31-8ae4-25ffc253453&title=&width=1469.0196353130646)
# 加号
相邻兄弟选择器
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1688403709815-420c58aa-c9e0-4124-9560-937dcace3645.png#averageHue=%23f5ecd4&clientId=u19314100-b26f-4&from=paste&height=540&id=u7fa39105&originHeight=688&originWidth=1920&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=239033&status=done&style=none&taskId=u38217891-9157-4257-8ddb-601206c88da&title=&width=1505.8823811004186)
如果.container 紧接的不是div 而是其他标签 就不会选取到
# 波浪号 ~
和加号很相似  通用兄弟选择器
只要是和.container 处于一个层级的后面的所有div无论有无隔档 都会被选取到
# nth-child  nth-of-type

- nth-child 选的是父元素下的第几个子类  而且这个类型必须是选的标签 不然不生效

![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1688404692743-73ae8ef5-1a22-4267-ab30-cc534a121e49.png#averageHue=%2370a26c&clientId=u19314100-b26f-4&from=paste&height=612&id=u79540bb2&originHeight=780&originWidth=1459&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=62204&status=done&style=none&taskId=u43e86078-1e64-4030-9bab-96f745b044e&title=&width=1144.313746888287)
这个就是ul的第一个子元素 但是这第一个子元素是span不是li 所以不生效  下面则生效
![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1688404707523-a63d0b0c-b5fc-4704-a9b9-5c1f1341c5be.png#averageHue=%2377a464&clientId=u19314100-b26f-4&from=paste&height=578&id=u3dc0b7bb&originHeight=737&originWidth=1482&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=54692&status=done&style=none&taskId=u4ae48091-e526-44c6-843a-7cb975477c4&title=&width=1162.3529629118857)

- nth-of-type  则是选子类这个标签类型的第几个

![image.png](https://cdn.nlark.com/yuque/0/2023/png/33778458/1688404783855-ea6c7cd4-9dfb-4aa3-b5a9-4670c81d068c.png#averageHue=%236d9f6c&clientId=u19314100-b26f-4&from=paste&height=613&id=ub21b4ce2&originHeight=782&originWidth=1534&originalType=binary&ratio=1.274999976158142&rotation=0&showTitle=false&size=69360&status=done&style=none&taskId=ub39da2f0-ee3b-48ca-a77f-bf86de856b6&title=&width=1203.137277400022)
这个选的是ul下的子元素li的第一个
# :not(:last-child)

选择父元素除了最后一个子元素的其他子元素