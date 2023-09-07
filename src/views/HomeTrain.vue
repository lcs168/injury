<template>
    <div class="common-layout" style="height: 100%;">
        <el-container style="height: 100%;">
        <el-aside width="10%" style="height: 100%;">
            <div style="height: 100%;display: flex;
                flex-direction: column;
                justify-content: space-around;">
            
            <el-card class="box-card">
                <el-image @click="selOne" class="imgTwo" :src="require('@/assets/leftimagebox/1.jpg')" alt="" style="height: 100%;" />
            </el-card>
            <el-card class="box-card">
                <el-image @click="selTwo" class="imgTwo" :src="require('@/assets/leftimagebox/2.jpg')" alt="" style="height: 100%;" />
            </el-card>
            <el-card class="box-card">
                <el-image @click="selThree" class="imgTwo" :src="require('@/assets/leftimagebox/3.jpg')" alt="" style="height: 100%;" />
            </el-card>
            <el-card class="box-card">
                <el-image @click="selFour" class="imgTwo" :src="require('@/assets/leftimagebox/4.jpg')" alt="" style="height: 100%;" />
            </el-card>
            <el-card class="box-card">
                <el-image @click="selFive" class="imgTwo" :src="require('@/assets/leftimagebox/5.jpg')" alt="" style="height: 100%;" />
            </el-card>
            <el-card class="box-card">
                <el-image @click="selSix" class="imgTwo" :src="require('@/assets/leftimagebox/6.jpg')" alt="" style="height: 100%;" />
            </el-card>
            </div>
        </el-aside>
        <el-main style="height: 100%;">
            <div style="width: 100%;display: flex;align-items: center;flex-direction: column;">
                <div>请点击上传图片</div>
                <el-upload
                    class="avatar-uploader"
                    action="https://run.mocky.io/v3/9d059bf9-4660-45f2-925d-ce80ad6c4d15"
                    :show-file-list="false"
                    :on-success="handleAvatarSuccess"
                    :before-upload="beforeAvatarUpload"
                >
                    <img v-if="imageUrl" :src="imageUrl" class="avatar" />
                    <el-icon v-else class="avatar-uploader-icon"><Plus /></el-icon>
                </el-upload>
            </div>
            <div style="width: 100%;height: 100%;">

                <el-card v-loading="loading" class="image" style="height: 60%;width: 100%;margin-top: 1%;">
                    <el-image :src="imageRes" alt="" style="width: 100%;height: 100%;">
                        <template #error>
                            <div class="image-slot">
                                <el-icon><Picture /></el-icon>
                            </div>
                        </template>
                    </el-image>
                </el-card>
            
            <router-link to="/study/right/fracture">
            <el-button type="primary" style="width:100%;margin-top: 1%;height: 5%;">
                识别为骨折，点击按钮向您推荐骨折救治方案
            </el-button>
            </router-link>
            </div>
        </el-main>
        </el-container>
    </div>
  </template>
  
<script>
import { ref } from 'vue'
import { Picture as IconPicture } from '@element-plus/icons-vue'

export default {
    name:"homeTrain",
    data(){
    return{
        // url:"require('@/assets/imagebox/gunshot/1.jpg')"
        videourl:"/videos/骨折识别.mp4",
        imageUrl : ref(''),
        loading : ref(''),
        imageRes: ref('')
    }
    },
    methods:{
    handleAvatarSuccess(response, uploadFile) {
      this.imageUrl = URL.createObjectURL(uploadFile.raw);
      this.showimage()
    //   this.loading = ref('')
    },
    showimage(){
        this.loading = ref('true')
        setTimeout(() => {
        this.loading = ref('')
        this.imageRes = require('@/assets/rightimagebox/1.jpg')

      }, 3000);
    },
    beforeAvatarUpload(rawFile) {
      if (rawFile.type !== 'image/jpeg') {
        this.$message.error('Avatar picture must be JPG format!');
        return false;
      } else if (rawFile.size / 1024 / 1024 > 2) {
        this.$message.error('Avatar picture size can not exceed 2MB!');
        return false;
      }
      return true;
    },
    selOne(){
        console.log('选择了')
        // this.videourl='/videos/撞伤救治.mp4'
        // window.location.replace("/homeTrain")
        location.reload();
    },
    selTwo(){
        console.log('选择了')
        location.reload();

    },
    selThree(){
        console.log('选择了')
        location.reload();

    },
    selFour(){
        console.log('选择了')
        location.reload();

    },
    selFive(){
        console.log('选择了')
        location.reload();

    },
    selSix(){
        console.log('选择了')
        location.reload();

    },
    aa(){
        router.push("/Information");
      },bb(){
        router.push("/Information");
      },cc(){
        router.push("/Information");
      },dd(){
        router.push("/Information");
      },ee(){
        router.push("/Information");
      },xiangshang(){
        router.push("/Information");
      },xiangxia(){
        router.push("/Information");
      },jietu(){
        router.push("/Information");
      },
      },
      created() 
    {
        // setTimeout(() => {
        this.$ws.addEventListener('message', (event) => {
        // 处理 WebSocket 消息
        const message = event.data;
        console.log('WebSocket消息：', message);
        
        if (message === 'aa_aa') {
            this.aa(); 
        } else if (message.includes('向上滑动')) {
            this.xiangshang();
        } else if (message.includes('向下滑动')) { 
            this.xiangxia();
        }  else if (message === 'bb_bb') {
            this.bb();
        } else if (message === '截图') {
            this.jietu();
        } else if (message === 'cc_cc') {
            this.cc();
        } else if (message === 'dd_dd') {
            this.dd();
        } else if (message === 'ee_ee') {
            this.ee();
        }


        })
        // }, 3000);  
        

    },
    mounted() {
    }
  }
</script>
  
<style>
.box-card{
    margin-left: 3%;
    height: 15% !important;
    cursor: pointer;
}

.box-card>.el-card__body{
    padding: 0 !important;
}
.image>.el-card__body{
    padding: 0 !important;
    height: 100%;
}
.image{
    margin-left: 0 !important;
}
.el-image{
    height: 85%;
    width: 100%;
}
.avatar-uploader .avatar {
  width: 10vw;
  height: 10vw;
  display: block;
}
.avatar-uploader .el-upload {
  border: 1px dashed var(--el-border-color);
  border-radius: 6px;
  cursor: pointer;
  position: relative;
  overflow: hidden;
  transition: var(--el-transition-duration-fast);
}

.avatar-uploader .el-upload:hover {
  border-color: var(--el-color-primary);
}

.el-icon.avatar-uploader-icon {
  font-size: 30px;
  color: #8c939d;
  width: 10vw;
  height: 10vw;
  text-align: center;
}

.image-slot {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  height: 100%;
  background: var(--el-fill-color-light);
  color: var(--el-text-color-secondary);
  font-size: 5vw;
}
</style>