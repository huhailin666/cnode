<template>
        <div class="article">
            <!-- 如果正在在加载显示此div -->
            <div class="loading" v-if="isLoading">
                <h1>正在加载</h1>
            </div>
            <div v-else>
                <div class="topic_header">
                    <div class="topic_title">{{post.title}}</div>
                    <ul>
                        <li>•发布于：{{post.create_at | formatDate}}</li>
                        <li>• 作者：
                        {{post.author.loginname}}
                        </li>
                        <li>• {{post.visit_count}}次浏览</li>
                        <li>•来自</li>
                    </ul>
                    <div v-html="post.content" class="topic_content"></div>
                </div>
                <div id="reply">
                    <div class="topbar">{{post.reply_count}}回复</div>
                    <div v-for="(reply,index)  in post.replies" class="replySec">
                        <div class="replyUp">
                            <router-link :to="{
                                    name:'user_info',
                                    params:{
                                        name:reply.author.loginname
                                    }
                                }">
                                <img :src="reply.author.avatar_url" alt="">
                            </router-link>
                        </div>
                        <router-link :to="{
                            name:'user_info',
                            params:{
                                name:reply.author.loginname
                            }
                            }">
                            <span class="loginname">{{reply.author.loginname}}</span>
                        </router-link>
                        <span>{{index+1}}楼</span>
                        <p v-html="reply.content"></p>
                    </div>
                </div>
            </div>
        </div>
    </template>
    <script>
        export default {
            name: 'Article',
            data(){
                return {
                    isLoading: false,
                    post:{}//代表当前文章页的所有内容
                }
            },
            methods: {
                getArticleData(){
                    this.$http.get('https://cnodejs.org/api/v1/topic/'+this.$route.params.id)
                        .then(res =>{
                            if(res.data.success == true){
                                this.isLoading = false;
                                console.log(res)
                                this.post = res.data.data
                            }
                        })
                        .catch(function(err){
                            console.log(err)
                        })
                }
            },
            beforeMount(){
                this.isLoading = true;
                this.getArticleData()
            },
            watch:{
                '$route'(to,from){
                // 通过 id 获取文章详情
                this.getArticleData()
                }
            }
        }
    </script>
    <style>
        @import url('../assets/markdown-github.css');
        a {
            text-decoration: none;
        }
        ul ,li {
            list-style : none;
        }
        .article {
            width: 680px;
            padding: 20px 10px;
            background-color: #fff;
            overflow: hidden;
        }
        .topic_header>ul>li {
            font-size: 12px;
            color: #838383;
            display: inline-block;
        }
        .topic_title {
            font-size: 22px;
        }
        .topic_header > ul {
            border-bottom: 1px solid #838383;
            padding-bottom: 10px;
        }
        /* 回复的样式 */
        .topbar {
            background-color: #f6f6f6;
            font-size: 14px;
            padding-top: 15px;
            padding-bottom: 15px;
        }
        .replyUp img {
            width: 30px;
            height: 30px;
            float: left;
        }
        .loginname {
            color: #666;
            font-size: 12px;
            padding-left: 10px;
        }
        .replySec>span:nth-child(3) {
            color: blue;
            font-size:12px;
        }
        .replySec {
            margin-top: 10px;
            margin-bottom: 20px;
            border-bottom: #e1e1e1;
        }
    </style>
    