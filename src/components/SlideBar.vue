<template>
    <div class="authorinfo">
        <div class="authoesummary">
            <p>作者</p>
            <div class="userhead" style="margin:10px;">
                <router-link :to="{
                    name:'user_info',
                    params:{
                        name:userinfo.loginname
                    }
                    }">
                    <img :src="userinfo.avatar_url" alt="">
                </router-link>
            
                <router-link :to="{
                    name:'user_info',
                    params:{
                        name:userinfo.loginname
                    }
                    }">
                    <span class="loginname">{{userinfo.loginname}}</span>
                </router-link>
            </div>
            <p class="score">积分：{{userinfo.score}}</p>
        </div>
        <div class="recent_replies">
            <p>作者最近主题</p>
            <ul>
                <li v-for="item in topiccount">
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
        <div class="recent_topics">
            <p>作者最近回复</p>
            <ul>
                <li v-for="item in repliescount ">
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
    </div>
</template>
<script>
    export default {
        name: 'UserInfo',
        data(){
            return {
                userinfo: {}
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
        computed: {
            topiccount(){
                if(this.userinfo.recent_topics.length > 5){
                    return this.userinfo.recent_topics.slice(0,5)
                }else{
                    return this.userinfo.recent_topics;
                }
            },
            repliescount(){
                if(this.userinfo.recent_replies.length > 5){
                    return this.userinfo.recent_replies.slice(0,5)
                }else{
                    return this.userinfo.recent_replies;
                }               
            }
        },
        beforeMount(){
            this.getData()
        },
        watch:{
            '$route'(to,from){
            // 通过 id 获取文章详情
            this.getData()
            }
        }
    }


</script>
<style>
    * {
        padding: 0;
        margin: 0;
    }
    ul,li {
        list-style: none;
    }
    .authorinfo {
        float: right;
        width: 300px;
    }
    .authoesummary img{
        width: 50px;
        height: 50px;
    }
    .loginname {
        font-size: 18px;
        color: #666;
    }
    p {
        padding: 10px;
        background-color: #f6f6f6;
    }
    .authorinfo >div {
        background: #fff;
        margin-bottom: 10px;
        margin-left: 10px;
    }
    .userhead {
        display: flex;
        align-items: center;
    }
    .score {
        background-color:#fff;
    }
    .authorinfo ul>li{
        overflow: hidden;
        white-space: nowrap;
        text-overflow: ellipsis;
        padding:10px;
    }
</style>