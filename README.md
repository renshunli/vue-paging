# vue-paging
分页 组件
基于vue-cli 开发的 vue 分页组件
此文件仅是单独.vue 自己导入到vue-cli工程里即可
# 使用方法
`<paging :total="orderList.total" :max="orderList.pages" @changePage="changePage"></paging>`

>total="orderList.total" total总共数据条数  
>max="orderList.pages" max最大页数  
>@changePage="changePage" changePage事件通知 当点击了分页分页会根据这个通知函数传回显示的页码
