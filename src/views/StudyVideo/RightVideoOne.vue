<template>

<div style="display: inline-block;float: right;width: 100%;height: 100%;margin-top: 1%;padding-left: 2%;">
            <span style="font-size: 2.5vh;">烧伤照片</span>
            <div style="display: flex;height: 5%;font-size: 1.8vh;align-items: center;">
            <el-divider style="margin: 0;border-width: 3px;border-color: black;" direction="vertical" />
            <span style="margin-left: 0.5%;">照片</span>
            </div>
            <div style="width: 100%;height: 88%;">
                <div style="height:100%">
                    <el-carousel :interval="3000000" indicator-color="#ff0000" style="height: 100%;">
                    <el-carousel-item v-for="(image, index) in imagebox" :key="index" style="height: 100%" indicator-color="#ff0000">
                        <img :src="image" class="carousel-image" alt="" style="height:100%;width:100%">
                    </el-carousel-item>
                    </el-carousel>
                </div>
        </div>
</div>

<!-- <div style="display: inline-block;float: right;width: 100%;height: 100%;margin-top: 1%;padding-left: 2%;">
        
    
    
    
        <span style="font-size: 2.5vh;">如何辨别烧伤？</span>
        <div style="display: flex;font-size: 1.8vh;align-items: center;">
        <el-divider style="margin: 0;border-width: 3px;border-color: black;" direction="vertical" />
        <span style="margin-left: 0.5%;">视频</span>
        </div>
        <div style="width: 90%;height: 100%;margin-top: 1%;">
        <video ref="myVideo" :poster="videoCover" controls style="width: 100%;height: 88%;">
            <source :src="videourl" type="video/mp4">
        </video>
        </div>
        </div> -->
</template>

<script>
import { ref } from 'vue';
export default {
    name:"RightVideoOne",
    data(){
        return{
            imagebox:[
            require('@/assets/imagebox/burn/1.jpg'),
            require('@/assets/imagebox/burn/2.jpg'),
            require('@/assets/imagebox/burn/3.jpg'),
            require('@/assets/imagebox/burn/4.jpg'),
            ],
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