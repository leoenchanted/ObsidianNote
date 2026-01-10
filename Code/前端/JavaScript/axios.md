# 基本使用
```javascript
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link href="https://cdn.bootcdn.net/ajax/libs/twitter-bootstrap/5.2.3/css/bootstrap-grid.min.css" rel="stylesheet">
    <script src="https://cdn.bootcdn.net/ajax/libs/axios/1.3.6/axios.min.js"></script>
</head>
<body>
    <div class="container">
       <h2 class="page-header">基本使用</h2>
       <button class="btn btn-primary">发送GET请求</button>
       <button class="btn btn-warning">发送POST请求</button>
       <button class="btn btn-success">发送PUT请求</button>
       <button class="btn btn-danger">发送DELETE请求</button>
    </div>
    <script>
        const btns = document.querySelectorAll('button');
        //第一个
        btns[0].addEventListener('click',function(){
            axios({
                method:'GET',
                url:'http://localhost:3000/posts/1',
            }).then(response=>{
                console.log(response);
            })
        })
        //添加一篇新得文章
        btns[1].addEventListener('click',function(){
            axios({
                method:'POST',
                url:'http://localhost:3000/posts',
                //设置请求体
                data:{
                    title:"今天真不错！",
                    author:"张张"
                }
            }).then(response=>{
                console.log(response);
            })
        })
        //更新数据
        btns[2].addEventListener('click',function(){
            axios({
                method:'PUT',
                url:'http://localhost:3000/posts/2',
                data:{
                    title:"今天真不错！",
                    author:"张效力"
            }}).then(response=>{
                console.log(response);
            })
        })
        //删除数据
        btns[2].addEventListener('click',function(){
            axios({
                method:'DELETE',
                url:'http://localhost:3000/posts/2',
            }).then(response=>{
                console.log(response);
            })
        })
        
    </script>
    
</body>
</html>
```
```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<div id="app">
    <button @click="search()">查询新闻信息</button>
</div>

<!-- 官网提供的 axios 在线地址 -->
<!--<script src="https://unpkg.com/axios/dist/axios.min.js"></script>-->
<script src="js/axios.js"></script>
<script src="js/vue.js"></script>
<script>
    new Vue({
        el: "#app",
        methods: {
            search(){
                //方式1：传入对象
                // axios({
                //     method:'GET',
                //     url:'http://localhost:3000/posts'
                // }).then(res=>{
                //     console.log(res);
                // })
                //方式2：常用方式
                axios.get("http://localhost:3000/posts")
                .then(res=>{
                    console.log(res);
                })
            }
        }
    })
</script>
</body>
</html>
```
## 异常处理
```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<div id="app">
    <button @click="search()">查询新闻信息</button>
</div>

<!-- 官网提供的 axios 在线地址 -->
<!--<script src="https://unpkg.com/axios/dist/axios.min.js"></script>-->
<script src="js/axios.js"></script>
<script src="js/vue.js"></script>
<script>
    new Vue({
        el: "#app",
        methods: {
            search(){
                axios.get("http://localhost:3000/posts")
                .then(res=>{
                    console.log(res);
                }).catch(reason=>{
                  console.log('异常触发了');
                  console.log(reason);
                })
            }
        }
    })
</script>
</body>
</html>
```
# 基本应用
## 默认配置
```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
</head>
<body>
<div id="app">
    <button @click="search">查询新闻信息</button>
    <ul>
        <li v-for="item in postList" :key="item.id">
            {{item.id}} {{item.title}} {{item.author}}
        </li>
    </ul>
</div>

<!-- 官网提供的 axios 在线地址 -->
<!--<script src="https://unpkg.com/axios/dist/axios.min.js"></script>-->
<script src="js/axios.js"></script>
<script src="js/vue.js"></script>
<script>
    axios.defaults.baseURL="http://localhost:3000";    //前面url很多一样相同，搞个默认配置
    new Vue({
        el: "#app",
        data:{
          postList:[]
        },
        methods: {
            search() {
                // 异常处理方式-建议
                axios.get("/posts")
                    .then(
                        res => {
                            console.log(res);
                            this.postList = res.data;
                        }
                    )
            }
        }
    })
</script>
</body>
</html>
```
# 

