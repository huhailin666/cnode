<template>
        <div class="header">
        <router-link :to="{name:'root'}">
            <img src="../assets/cnode.svg" alt="">
        </router-link>
        <ul>
                <li><a href="">首页</a></li>
                <li><a href="">新手入门</a></li>
                <li><a href="">API</a></li>
                <li><a href="">关于</a></li>
                <li><a href="">注册</a></li>
                <li><a href="">登录</a></li>
            </ul>
        </div>
    </template>
    <script>
        export default {
            name: 'Header'
        }
    </script>
    <style scoped>
        /* 加scoped表示这里的样式只对当前页面有效 */
        .header {
            background: #5a5555;
            height: 50px;
        }
        img{
            width: 120px;
            margin-left: 50px;
            margin-top: 10px;
        }
        ul{
            list-style: none ;
            float: right;
            margin: 4px;
        }
        li {
            display: inline-block;
            padding: 10px 15px;
            border-bottom: none;
        }
        a{
            text-decoration: none;
            color: #ccc;
            font-size: 14px;
            text-shadow: none;
        }
    </style>
    