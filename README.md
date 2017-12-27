# vue-paging
分页 组件
基于vue-cli 开发的 vue 分页组件
此文件仅是单独.vue 自己导入到vue-cli工程里即可


# 参数说明
`<paging :nowPageOnOff="nowPageOnOff" :total="list.total" :max="list.pages" @changePage="changePage"></paging>`
>total="total" 
 total总共数据条数  
>max="pages" 
 max最大页数  
>@changePage="changePage" 
  changePage事件通知 当点击了分页分页会根据这个通知函数传回显示的页码  你在用返回的页面去服务器请求数据
>nowPageOnOff true or false 
  当这个状态改变以后会触发changePage() 并且返回 第一页，一般用于获取了新的数据列表重置到第一页。


代码例子:
```data(){
    return {
        nowPageOnOff : true,
        list : {
           total : 100, //100条数据 
           pages : 10, //最大页数 10  每页显示10条
        }
    },
    methods{
        changepage(page){
            console.log(page) //当点击了页码会触发这个回调函数。 返回当前点击的页数。根据这个页数去服务器请求数据
            $.ajax({
                method  : 'GET',
                url : ****** + page,
                success(res){
                    res.list.total = 100; //total需要后台返回我们在这里只是模拟
                    res.list.pages = 10; //pages需要后台返回我们在这里只是模拟
                    this.list = res.list;
                    this.nowPageOnOff = !this.nowPageOnOff
                }
            })
        }
    }
}```


