<template>
        <div id="app">
            <Header></Header>
            <main>
                <router-view name="slidebar"></router-view>
                <router-view name="main"></router-view>        
            </main>
        </div>
    </template>

<script>
        import Header from './components/Header.vue'
        import Article from './components/Article.vue'
        import PostList from './components/PostList.vue'
        import UserInfo from './components/UserInfo.vue'

        export default {
            name: 'App',
            components: {
              Header,PostList,Article,UserInfo
            }
        }
</script>

<style>
body {
    background-color:#e1e1e1
}
main {
    width: 1000px;
    margin: 10px auto;
}
</style>
