
<template>
        <div class = "postlist">
            <div v-if="isLoading">
                <h1>正在加载</h1>
            </div>
            <div v-else>
                <ul>
                    <li class="topBar">
                        
                            <span>全部</span>
                            <span>精华</span>
                            <span>分享</span>
                            <span>问答</span>
                            <span>招聘</span>
                        
                    </li>
                    <li v-for="post in posts">
                        <!-- 头像 -->
                        <img :src="post.author.avatar_url" alt="">
                        <span class="ask">
                            <!-- 回复/；浏览 -->
                            <span >{{post.reply_count}}</span>
                            /
                            <span>{{post.visit_count}}</span>
                        </span>
    
                        <!-- 帖子分类 -->
                        <span :class="[{put_good:(post.good == true)},{put_top:(post.top == true)},
                        {topiclist_tab:(post.good != true)&&(post.top != true)}]">{{post | tabFormatter}}</span>
                        <!-- 标题 -->
                            <router-link :to="{
                                name:'post_content',
                                params: {
                                    id: post.id,
                                    name: post.author.loginname
                                }
                            }">
                                <span class="title">{{post.title}}</span>
                            </router-link>
    
                        <!-- 最终回复时间 -->
                        <span class="last_reply">{{post.last_reply_at | formatDate}}</span>               
                    </li>
                    <li>
                        <pagination @handle="renderList"></pagination>
                    </li>
                </ul>
            </div>
        </div>
    </template>
    <script>
        import Vue from 'vue'
        import pagination from './Pagination'
    
        
        export default {
            name: 'PostList',
            data(){
                return {
                    isLoading: false,
                    posts : [],
                    noneClass:'noneClass',
                    postPage:1
                }
            },
            components:{
                pagination
            },
            methods: {
                getData(){
                    var self = this
                    this.$http.get('https://cnodejs.org/api/v1/topics',{
                        params:{
                            page:self.postPage,
                            limit:20
                        }
                    })
                    .then(function(res){
                        self.isLoading = false
                        self.posts = res.data.data
                    })
                    .catch(function(err){
                        console.log(err)
                    })
                },
                renderList(value){
                    this.postPage = value;
                    this.getData()
                }
            },
            beforeMount(){
                this.isLoading = true  //加载前显示加载动画
                this.getData()
            }
        }
    </script>
    <style>
        img {
            width: 30px;
            height: 30px;
            float: left;
        }
        .loading{
            display: none;
        }
        * {
            padding: 0;
            margin: 0;
            box-sizing: border-box;
        }
        ul ,li {
            list-style: none;
        }
        .postlist {
            max-width: 1000px;
            margin: 0 auto;
            background: #fff;
            padding: 10px;
        }
        .topBar {
            background-color: #f6f6f6;
        }
        .topBar>span {
            color: #80bd01;
            padding: 15px;
        }
        ul>li {
            padding-top:10px;
            padding-bottom:10px; 
            border-bottom: 1px solid #f6f6f6;
            
        }
        ul>li>span {
            line-height: 30px;
        }
        ul>li:first-child {
            padding-top:10px;
            padding-bottom:10px;
        }
        .last_reply {
            float: right;
            font-size: 11px;
            color: #777;
        }
        .put_good , .put_top{
            color: #fff;
            font-size: 12px;
            background: #80bd01;
            padding: 5px;
            border-radius: 2px;
        }
        .topiclist_tab {
            font-size: 12px;
            background-color: #e5e5e5;
            color: #999;
            padding: 5px;
            border-radius: 2px;
        }
        .ask {
            display: inline-block;
            width: 100px;
            text-align: center;
            font-size: 14px;
        }
        .ask>span:first-child {
            color: #9e78c0;
            font-size: 14px;
        }
        .ask>span:last-child {
            font-size: 10px;
            color: #b4b4b4;
        }
        .title {
            display: inline-block;
            width: 700px;
            overflow: hidden;
            white-space: nowrap;
            text-overflow: ellipsis;
        }
    </style>
    