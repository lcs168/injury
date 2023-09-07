<template>

    <div style="display: inline-block;float: right;width: 100%;height: 100%;margin-top: 1%;padding-left: 2%;">
                <div style="width: 100%;height: 88%;">
                    <div style="height:100%">
                        <el-carousel :interval="3000000" indicator-color="#ff0000" style="height: 100%;">
                        <el-carousel-item style="height: 100%" indicator-color="#ff0000">
                            <img :src="imagebox" class="carousel-image" alt="" style="height:100%;width:100%">
                        </el-carousel-item>
                        </el-carousel>
                        <div style="display: flex;justify-content: space-evenly;margin-top: 1%;">
                        <el-button type="primary">增加节点</el-button>
                        <el-button type="primary">删除节点</el-button>
                        <el-button type="primary">修改节点</el-button>
                        <el-button type="primary">查询节点</el-button>
                        </div>
                    </div>
            </div>
    </div>
    </template>
    
    <script>
    import { ref } from 'vue';
    export default {
        name:"RightVideoOne",
        data(){
            return{
                imagebox:
                require('@/assets/imagebox/默认.jpg'),
                videourl:"/videos/烧伤救治.mp4",
            }
        },
    }
    </script>
    
    <style>
    .el-carousel__container{
        height: 100%;
    }
    </style>