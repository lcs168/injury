<template>
    <div style="display: inline-block;float: right;width: 100%;height: 100%;margin-top: 1%;padding-left: 2%;">
            <div style="width: 90%;height: 100%;margin-top: 1%;">
                <div style="display: flex;font-size: 1.8vh;align-items: center;">
                    <el-divider style="margin: 0;border-width: 3px;border-color: black;" direction="vertical" />
                    <span style="margin-left: 0.5%;">药品和工具</span>
                </div>
                <div style="padding:1%;border-radius:10px;border:2px solid #dcdfe6">
                    <el-scrollbar height="50vh">
                        <el-text size="default" tag="p">
                            止血带、美洛昔康片、对乙酰氨基酚片
                        </el-text>
                    </el-scrollbar>
                </div>
            </div>
            </div>
</template>

<script>
import RightVideoOneVue from '../StudyVideo/RightVideoOne.vue'
export default {
    name:"burnDrug",
    data(){
        return{
            imagebox:[
            require('@/assets/imagebox/burn/1.jpg'),
            require('@/assets/imagebox/burn/2.jpg'),
            require('@/assets/imagebox/burn/3.jpg'),
            require('@/assets/imagebox/burn/4.jpg'),

            ],
            videourl:"/videos/烧伤救治.mp4"
        }
    },
    components:{
        RightVideoOneVue,
    }
}
</script>

<style>
.el-carousel__item h3 {
  color: #475669;
  opacity: 0.75;
  line-height: 300px;
  margin: 0;
  text-align: center;
}

.el-carousel__item:nth-child(2n) {
  background-color: #99a9bf;
}

.el-carousel__item:nth-child(2n + 1) {
  background-color: #d3dce6;
}
.el-carousel{
    height: 90%;
}
.el-carousel__container{
    height: 100%;
}
.scrollbar-demo-item {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 50px;
  margin: 10px;
  text-align: center;
  border-radius: 4px;
  background: var(--el-color-primary-light-9);
  color: var(--el-color-primary);
}
p{
    line-height: 4vh;
}
</style>