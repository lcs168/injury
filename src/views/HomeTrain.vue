<template>
  <div class="main">
    <div class="content">
      <!--        左侧图表    -->
      <div class="left-content">

        <div class="container">
          <div class="centered-text">伤情数据加载</div>
          <div class="buttons">

            <el-button style="width:100px; font-size: 24px" size="big" type="primary" @click="downloadData">拍摄</el-button>
            <el-button style="width:100px; font-size: 24px" size="big" type="primary" @click="downloadData">载入</el-button>

          </div>
          <div class="centered-text">伤情数据记录</div>
          <div class="image-container" >
              <div class="slide" :class="{ 'selected': selectedImageIndex === index }" v-for="(image, index) in images" :key="index" >
                <img :src="image" alt="图片" class="bordered-image" @click="selectImage(index)" />
              </div>

          </div>
        </div>




      </div>
      <!--        右侧数据表-->
      <div class="right-content">
        <div class="centered-text">伤情实时识别</div>
        <div class="container" >
          <div class="container1 left-column" >
            <img :src="require('@/assets/leftimagebox/2.jpg')" alt="图片" class="bordered-image"/>
          </div>
          <div class="image-container right-column" >

              <div class="slide" v-for="(image, index) in images1" :key="index">
                <img :src="image" alt="图片" class="bordered-image"/>
              </div>


          </div>
        </div>
        <div class="centered-text">救治方案推荐</div>

        <!-- <div>
          <button @click="speakText">播放语音</button>
        </div> -->
        <div class="box">
          <span style="width: auto; font-family: bond; font-size: 20px; margin: 0 40px 0 40px">识别结果</span>
          <span style="width: auto; font-family: bond; font-size: 20px; margin: 0 40px 0 40px">{{0.88}}</span>


          <el-button style="width:180px; font-size: 24px; margin: 0 40px 0 40px" size="big" type="primary" @click="speakText">推荐方案1</el-button>
          <audio ref="audioElement" @canplaythrough="startPlayback">
            <source src="C:\Users\11985\Desktop\0905\admin-front\admin-front\public\MP3\盛夏-毛不易.320.mp3" type="audio/mpeg">您的浏览器不支持音频播放。
          </audio>
          <!-- <el-button style="width:180px; font-size: 24px; margin: 0 40px 0 40px" size="big" type="primary" @click="downloadData">推荐方案2</el-button>
          <el-button style="width:180px; font-size: 24px; margin: 0 40px 0 40px" size="big" type="primary" @click="downloadData">推荐方案3</el-button> -->

        </div>
        <div class="box1">
          <span style="width: auto; font-family: bond; font-size: 20px; margin: 0 40px 0 40px">识别结果</span>
          <span style="width: auto; font-family: bond; font-size: 20px; margin: 0 40px 0 40px">{{0.88}}</span>


          <el-button style="width:180px; font-size: 24px; margin: 0 40px 0 40px" size="big" type="primary" @click="downloadData">推荐方案1</el-button>
          <el-button style="width:180px; font-size: 24px; margin: 0 40px 0 40px" size="big" type="primary" @click="downloadData">推荐方案2</el-button>
          <el-button style="width:180px; font-size: 24px; margin: 0 40px 0 40px" size="big" type="primary" @click="downloadData">推荐方案3</el-button>

        </div>
        <div class="box1">
          <span style="width: auto; font-family: bond; font-size: 20px; margin: 0 40px 0 40px">识别结果</span>
          <span style="width: auto; font-family: bond; font-size: 20px; margin: 0 40px 0 40px">{{0.88}}</span>


          <el-button style="width:180px; font-size: 24px; margin: 0 40px 0 40px" size="big" type="primary" @click="downloadData">推荐方案1</el-button>
          <el-button style="width:180px; font-size: 24px; margin: 0 40px 0 40px" size="big" type="primary" @click="downloadData">推荐方案2</el-button>
          <el-button style="width:180px; font-size: 24px; margin: 0 40px 0 40px" size="big" type="primary" @click="downloadData">推荐方案3</el-button>

        </div>



      </div>
    </div>
  </div>
</template>

<script>
export default {
  
  name:"homeTrain",
  data(){
    return{
      // url:"require('@/assets/imagebox/gunshot/1.jpg')"
      videourl:"/videos/骨折识别.mp4",
      videourl1:"././",
      images: [
        require('@/assets/leftimagebox/1.jpg'),require('@/assets/leftimagebox/2.jpg'),require('@/assets/leftimagebox/3.jpg'),require('@/assets/leftimagebox/4.jpg'),
      ],
      images1: [
        require('@/assets/leftimagebox/5.jpg'),require('@/assets/leftimagebox/6.jpg'),require('@/assets/leftimagebox/1.jpg')
      ],
      selectedImageIndex: 1,
      output: '' // 初始化一个空字符串来存储输出的文本
    }
  },
  
  methods:{
    selectImage(index){
      this.selectedImageIndex = index;
      console.log('选择了')

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
    
    playAudio() {
      const audioElement = this.$refs.audioElement;
      this.output = '1'
      // 在这里不直接播放，等待 canplaythrough 事件触发后再播放
    },
    startPlayback() {
      const audioElement = this.$refs.audioElement;
      audioElement.play();
      
    },
    pauseAudio() {
      const audioElement = this.$refs.audioElement;
      audioElement.pause();
    },
    speakText() {
      // 检查浏览器是否支持SpeechSynthesis API
      if ('speechSynthesis' in window) {
        const speechSynthesis = window.speechSynthesis;
        const textToSpeak = '你好，这是一个语音示例。'; // 要合成的文本

        // 创建一个SpeechSynthesisUtterance对象
        const utterance = new SpeechSynthesisUtterance(textToSpeak);

        // 使用默认的语音
        utterance.voice = speechSynthesis.getVoices()[0];

        // 开始语音合成
        speechSynthesis.speak(utterance);
      } else {
        alert('抱歉，你的浏览器不支持语音合成功能。');
      }
    }
  }
}
</script>

<style lang="scss">
.main {
  //min-width: 1536px;
  user-select: none;
  position: relative;

  .content {
    display: flex;

    .left-content {
      width: 15%;
      height: auto;
      margin: 20px 1.5% 60px 3.5%;
      // align-items: center;
      // justify-content: space-between;

      .container {
        display: flex;
        flex-direction: column;
        align-items: center;
      }

      .centered-text {
        font-size: 30px;
        font-family: bond;
        text-align: center;
        margin: 20px 0 20px 0;
      }

      .button-container {
        display: flex;
        justify-content: center;
        margin-bottom: 20px;
      }
      .image-container {
        width: 100%;
        height: 600px; /* 高度自适应保持图片比例 */
        overflow: scroll;
        display: flex;
        flex-direction: column;
        box-sizing: border-box; /* 计算边框和内边距在容器尺寸内 */
        border: 1px solid #ddd; /* 外边框样式 */
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); /* 阴影样式 */
        padding: 10px; /* 内边距 */
      }



      .slider {
        display: flex;
        width: max-content;
      }

      .slide {
        flex-shrink: 0;
        margin-bottom: 10px;

        .bordered-image {
          border: 1px solid #000; /* 边框样式 */
          width: 100%; /* 宽度为容器的百分之百 */
          height: auto; /* 高度自适应保持图片比例 */
          box-sizing: border-box; /* 将边框计入图片尺寸内 */
        }
      }
      .selected {
        border: 2px solid red;
      }
      .buttons {
        display: flex;
        align-items: center;
        justify-content: space-between;

        .add_button {
          width: 35px;
          height: 35px;
          border: none;
          cursor: pointer;
          background-color: #eeeeee00;
        }

        .button-group {
          display: flex;
          margin-left: 20px;
        }
      }


    }

    .right-content {
      width: 75%;
      height: auto;
      margin: 20px 1.5% 60px 3.5%;
      align-items: center;
      justify-content: space-between;



      .centered-text {
        font-size: 30px;
        font-family: bond;
        margin: 20px 0 20px 20px;
      }

      .button-container {
        display: flex;
        justify-content: center;
        margin-bottom: 20px;
      }


      .container {
        width: 100%;
        height: 450px; /* 高度自适应保持图片比例 */
        overflow: hidden;

        display: flex;
        box-sizing: border-box; /* 计算边框和内边距在容器尺寸内 */
        border: 1px solid #ddd; /* 外边框样式 */
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); /* 阴影样式 */
        padding: 10px; /* 内边距 */
      }

      .container1 {
        width: 60%;
        height: 80%;
        margin: 0 5% 0 5%;

        display: flex;
        flex-direction: column;
        .bordered-image {

          width: auto;
          height: 420px;
          border: 1px solid #000; /* 边框样式 */
          box-sizing: border-box; /* 将边框计入图片尺寸内 */
        }
      }

      .image-container {
        width: 30%;
        height: 100%; /* 高度自适应保持图片比例 */

        display: flex;
        flex-direction: column;
        overflow: scroll;
        box-sizing: border-box; /* 计算边框和内边距在容器尺寸内 */
        border: 1px solid #ddd; /* 外边框样式 */
        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1); /* 阴影样式 */
        padding: 10px; /* 内边距 */
      }

      .slider {
        display: flex;
        width: max-content;
      }

      .slide {
        flex-shrink: 0;
        margin-bottom: 10px;

        .bordered-image {
          border: 1px solid #000; /* 边框样式 */
          width: 100%; /* 宽度为容器的百分之百 */
          height: auto; /* 高度自适应保持图片比例 */
          box-sizing: border-box; /* 将边框计入图片尺寸内 */
        }












      }
      .box{
        margin: 0 0 15px 0;
        padding: 10px; /* 内边距 */
        background-color: #99a9bf;
      }
      .box1{
        margin: 0 0 15px 0;
        padding: 10px; /* 内边距 */
        background-color: #FFFFFF;
      }
    }

  }
}

</style>



homeTrain