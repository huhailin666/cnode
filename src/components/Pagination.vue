<template>
        <div class="pagination">
            <button @click="changeBtn" class="btn">首页</button>
            <button @click="changeBtn" class="btn">上一页</button>
            <button v-if="judge">...</button>
            <button v-for="btn in pagebtns" :class="['pagebtns',{'currentpage':(btn == currentPage)}]" @click="changeBtn(btn)">
                {{btn}}
            </button>
            <button>...</button>
            <button @click="changeBtn" class="btn">下一页</button>    
       </div>
    </template>
    <script>
        import $ from 'jquery'

        export default {
            name: 'Pagination',
            data(){
                return {
                    pagebtns: [1,2,3,4,5],
                    currentPage:1,
                    judge:false
                }
            },
            methods: {
                changeBtn(page){
                    //点击上一页，下一页，首页
                    if(typeof page !='number'){
                        switch(page.target.innerText){
                            case '上一页':
                                $('button.currentpage').prev().click();
                                break;
                            case '下一页':
                                $('button.currentpage').next().click();
                                break;
                            case '首页' :
                                this.pagebtns=[1,2,3,4,5];
                                this.changeBtn(1);
                                break;
                            default: 
                                break;
                        }
                        return;
                    }
                    this.currentPage=page;
                    if(page==this.pagebtns[4]){
                        this.pagebtns.shift() //移除第一个参数
                        this.pagebtns.splice(4,0,this.pagebtns[3]+1)
                    }else if(page==this.pagebtns[0]&&page!=1){
                        this.pagebtns.unshift(this.pagebtns[0]-1)
                        this.pagebtns.splice(5,1)
                    }
                    if(this.pagebtns[0]==1){
                        this.judge=false;
                    }else{
                        this.judge=true;
                    }
                    this.$emit('handle',this.currentPage)
                }
            },
            
        }
    </script>
    <style>
        button {
            width: 30px;
            padding: 5px;
            font-size: 14px;
            margin: 5px;
            border-radius: 3px;
            background-color: #fff;

        }
        .currentpage {
            background-color: #ccc;
        }
        .btn {
            width: 50px;
            font-size: 10px;
            padding-top: 5px;
            padding-bottom: 5px;
        }
        .pagination {
            border: 1px solid #ccc;
            border-radius: 5px;
            margin: 0 auto;
            text-align: center;
        }

    </style>