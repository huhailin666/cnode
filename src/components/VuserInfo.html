<template>
        <div class="UserInfo">
            <div class="loading" v-if="isLoading">
                <h1>正在加载</h1>
            </div>
            <div class="UserInformation" v-else>
                <p>主页/</p>
                <section>
                        <img :src="userinfo.avatar_url" alt="">
                        <span>{{userinfo.loginname}}</span>
                        <p>{{userinfo.score}}积分</p>
                        <p>注册时间： {{userinfo.create_at | formatDate}}</p>
                </section>
                <section>
                    <div class="replies">
                        <p>参与的话题</p>
                        <ul>
                            <li v-for="item in userinfo.recent_replies ">
                                <router-link :to="{
                                    name:'post_content',
                                    params:{
                                        id: item.id,
                                        name: item.author.loginname
                                    }
                                }">
                                    {{item.title}}
                                </router-link>
                            </li>
                        </ul>
                    </div>
                    <div class="topics">
                        <p>创建的主题</p>
                        <ul>
                            <li v-for="item in userinfo.recent_topics">
                                <router-link :to="{
                                    name:'post_content',
                                    params:{
                                        id: item.id,
                                        name: item.author.loginname
                                    }
                                }">
                                    {{item.title}}
                                </router-link>                        
                            </li>
                        </ul>
                    </div>
                </section>
            </div>
        </div>
    </template>
    <script>
        export default {
            name: 'UserInfo',
            data(){
                return {
                    isLoading:false,
                    userinfo:{}
                }
            },
            methods: {
                getData(){
                    this.$http.get(`https://cnodejs.org/api/v1/user/${this.$route.params.name}`)
                        .then(res=>{
                            this.isLoading=false
                            this.userinfo = res.data.data
                            console.log(res)
                        })
                        .catch(function(err){
                            console.log(err)
                        })
                }
            },
            beforeMount(){
                this.getData()
            }
        }
    </script>
    <style>
        /* 公共样式 */
        * {
            padding: 0;
            margin: 0;
        }
        ul ,li {
            list-style: none;
        }
        a {
            text-decoration: none;
        }

        .UserInfo {
            width: 900px;
            margin: 0 auto;

        }
        .UserInformation > p{
            padding-top: 10px;
            padding-bottom: 10px;
            color: #f6f6f6;
            border-radius: 4px;
        }
        /* 第一块 */
        .UserInformation>section {
            border: 1px solid #f6f6f6;
            margin: 20px;
        }
        .UserInformation> section> img {
            width: 40px;
            height: 40px;
        }
        .loginname,.registerTime {
            color: #666;
            font-size: 12px;
            padding-left: 10px;
        }
        .replies> p,.topics>p{
            padding: 10px;
            background-color: #f6f6f6;
        }

        .topics>ul>li,.replies>ul>li {
            padding: 10px; 
            border-bottom: 1px solid #f6f6f6;
        }

    </style>
            