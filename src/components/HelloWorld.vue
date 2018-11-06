<template>
  <div class="hello" style="position: relative;overflow:hidden;">
    <div class="body-width" :class="(jiazaiAnimate)?'jiazai-animate':'' " v-show="(jiazaiAnimate==1)" >
      <div style="width:100%;height:100%;position:relative">
        <div class="tiao">
          <div class="zhi"></div>
          <div class="jiazai">{{jiazaiNum}}%</div>
        </div>
      </div>
    </div>
    <div class="body-width" style="background-color: #9AE1FA;" id="page1" 
    @touchstart.prevent="touchStart" 
    @touchmove.prevent="touchMove"
    @touchend="touchEnd(1)">
      <div style="width:100%;height:100%;position:relative">
        <div class="page1-top"><img src="../assets/page1-top.png"></div>
        <div class="page1-head"><img src="../assets/page1-head.png"></div>
        <img src="../assets/cloud.png" class="page1-cloud1">
        <img src="../assets/cloud.png" class="page1-cloud2">
        <img src="../assets/caihong.png" class="page11-caihong">
        <div class="page1-word1"></div>
        <img src="../assets/page1-word2.png" class="page1-word2">
        <img src="../assets/page1-word3.png" class="page1-word3">
        <img src="../assets/page1-word4.png" class="page1-word4">
        <img src="../assets/page1-word5.png" class="page1-word5">
        <img src="../assets/page1-star1.png" class="page1-star1">
        <img src="../assets/page1-star2.png" class="page1-star2">
        <img src="../assets/page1-qiqiu1.png" class="page1-qiqiu1">
        <img src="../assets/page1-qiqiu2.png" class="page1-qiqiu2">
        <img src="../assets/page1-qiqiu3.png" class="page1-qiqiu3">
        <img src="../assets/page1-people1.png" class="page1-people1">
        <img src="../assets/page1-people2.png" class="page1-people2">
        <div class="cloud cloudA">
          <!-- <div class="cloud-1"></div>
          <div class="cloud-2"></div> -->
          <img src="../assets/huojian.png">
        </div>
       <!--  <div class="sky">
            <div class="clouds_one"></div>
            <div class="clouds_two"></div>
            <div class="clouds_three"></div>
        </div> -->
        <div class="wrap center">
          <div class="img1 move1"></div>
          <div class="img2 move2"></div>
          <div class="img3 move3"></div>
        </div>
      </div>
    </div>
    <div class="body-width" id="page2" @touchstart.prevent="touchStart" 
    @touchmove.prevent="touchMove"
    @touchend="touchEnd(2)">
      <img src="../assets/page2-yijia.png" class="page2-yijia">
      <div class="page2-yijianei">
        <img src="../assets/page2-img1.jpg" class="page2-img1">
        <img src="../assets/page2-img2.jpg" class="page2-img2">
        <img src="../assets/page2-img3.jpg" class="page2-img3">
        <img src="../assets/page1-top.png" class="page2-caiqi">
      </div>
      <img src="../assets/page2-word.png" class="page2-word">
      <img src="../assets/page2-sun.png" class="page2-sun">
      <img src="../assets/page1-qiqiu1.png" class="page2-qiqiu1">
      <img src="../assets/page1-qiqiu2.png" class="page2-qiqiu2">
      <img src="../assets/page2-hengxian.png" class="page2-hengxian">
      
    </div>
    <div class="body-width" id="page3" @touchstart.prevent="touchStart" 
    @touchmove.prevent="touchMove"
    @touchend="touchEnd(3)">
      <img src="../assets/6.jpg" class="page3-img3">
      <img src="../assets/7.jpg" class="page3-img4">
      <img src="../assets/8.jpg" class="page3-img5">
      <img src="../assets/page3-word2.png" class="page3-word2">
      <img src="../assets/page3-word3.png" class="page3-word3">
      <img src="../assets/page3-word4.png" class="page3-word4">
    </div>

    <div class="body-width" id="page4" @touchstart.prevent="touchStart" 
    @touchmove.prevent="touchMove"
    @touchend="touchEnd(4)">
      <img src="../assets/9.jpg" class="page3-img6">
      <img src="../assets/10.jpg" class="page3-img7">
      <img src="../assets/page3-word5.png" class="page3-word5">
    </div>
    <div class="body-width" id="page5" @touchstart.prevent="touchStart" 
    @touchmove.prevent="touchMove"
    @touchend="touchEnd(5)">
      <img src="../assets/11.jpg" class="page3-img8">
      <img src="../assets/12.jpg" class="page3-img9">
      <img src="../assets/13.jpg" class="page3-img10">
      
      <img src="../assets/page3-word6.png" class="page3-word6">
      <img src="../assets/page3-word7.png" class="page3-word7">
      <img src="../assets/page3-word8.png" class="page3-word8">
    </div>
    <div class="body-width" id="page6" @touchstart.prevent="touchStart" 
    @touchmove.prevent="touchMove"
    @touchend="touchEnd(6)">
      <img src="../assets/14.jpg" class="page3-img11">
      <img src="../assets/15.jpg" class="page3-img12">
      <img src="../assets/page3-word9.png" class="page3-word9">
    </div>

    <div class="body-width" id="page7" @touchstart.prevent="touchStart" 
    @touchmove.prevent="touchMove"
    @touchend="touchEnd(7)">
      <img src="../assets/page1-top.png" class="page1-caiqi">
      <img src="../assets/page4-word1.png" class="page4-word1">
      <img src="../assets/page4-word2.png" class="page4-word2">
      <div class="daojishi">
        {{page4Day}}天{{page4Hour}}小时{{page4Min}}分{{page4Sec}}秒
      </div>

      <img src="../assets/daohang.png" @click="daohang" class="daohang" >
      <div class="allmap" style="position:absolute;right:-100%;z-index:98;width:100%;height:100%;transition: all 1s ease;">
        <div id="allmap" style="width:100%;height:100%;"></div>
        <img src="../assets/guanbi.png" class="guanbi" style="position:absolute;bottom:20px;left:50%;width:30px;z-index:9999;" @click="guanbi">
      </div>
      <img src="../assets/page4-bottom.png" class="page4-bottom">
    </div>

    <!-- up&down -->
    <div class="shanghua" v-show="downShow"></div>
    <div class="xiahua" v-show="upShow"></div>
    <div id="audio_btn" class="moren-rotate" @click="bofang" >
      <audio loop  id="media"  preload="">
        <source src="../assets/music.mp3" type="">
      </audio>
    </div>


  </div>
</template>

<script>
import $ from 'jquery'
import BMap from 'BMap'
export default {
  name: 'HelloWorld',
  data () {
    return {
      message: 'Hello Vue.js!',
      jiazaiNum:0,
      jiazaiAnimate:1,
      panduan:0,
      page:0,
      downShow:false,
      upShow:false,
      page4Day : 20,
      page4Hour:  20,
      page4Min : 20,
      page4Sec : 20,
      bofangcishu:2,
      playLogo:true,
      jishu:0,
      page3Time:true,
    }
  },
  created() {
    this.touch = {}
  },
  watch: {
    page: function () {
      if(this.page == 1){
        this.downShow = true
        this.upShow = false
      }else if(this.page == 7){
        this.downShow = false
        this.upShow = true
      }else{
        this.downShow = true
        this.upShow = true
      }
      this.fuyuan()
      this.pageShow()
    }
  },
  mounted(){
    $(".hello").width($(window).width())
    $(".hello").height($(window).height())
    var that = this
    // dingshiqi
    var interval = setInterval(function () {
        that.jiazaiNum++
        if (that.jiazaiNum >= 100) {
            clearInterval(interval)
            $(".jiazai-animate").animate({
              width:"0px"
            },1000)
            var t=setTimeout(function(){
              that.page = 1
              
            },1000)
        }
    }, 1)

    var timerInterval =  setInterval(function(){
      //获取当前时间  
      var date = new Date();  
      var now = date.getTime();  
      //设置截止时间  
      var str="2018/11/17 17:18:00";
      var endDate = new Date(str); 
      var end = endDate.getTime();  
      //时间差  
      var leftTime = end-now; 
       //定义变量 d,h,m,s保存倒计时的时间  
       var d,h,m,s;  
       if (leftTime>=0) {  
          d = Math.floor(leftTime/1000/60/60/24);  
          h = Math.floor(leftTime/1000/60/60%24);  
          m = Math.floor(leftTime/1000/60%60);  
          s = Math.floor(leftTime/1000%60);                     
       }else{
          clearInterval(timerInterval)
       } 
       //将倒计时赋值到div中 
       that.page4Day =  d
       that.page4Hour =  h
       that.page4Min =  m
       that.page4Sec =  s

    },1000) 
    var map = new BMap.Map("allmap");          // 创建地图实例  
    map.centerAndZoom(new BMap.Point(121.26083,30.194382), 25);      
    // 创建地址解析器实例     
    var myGeo = new BMap.Geocoder();      
    // 将地址解析结果显示在地图上，并调整地图视野    
    myGeo.getPoint("浙江省宁波市慈溪市孙塘北路1358号", function(point){      
        if (point) {      
            map.centerAndZoom(point, 16);      
            map.addOverlay(new BMap.Marker(point));      
        }      
     }, 
    "宁波市");
  },
  methods:{
    bofang(){
      var audio = document.querySelector('#media');
      $("#audio_btn").toggleClass("rotate"); //控制音乐图标 自转或暂停
      //控制背景音乐 播放或暂停            
      if($("#audio_btn").hasClass("rotate")){
        audio.play();
      }else{
        audio.pause();
      }

    },
    pageShow(){
      // 第一页动画
      if(this.page == 1){
        $('.page1-top').css("top","-10px")
        $(".page1-head").css({"height":"180px","width":"180px",'margin-left':"-90px"})
        $(".page1-star2").css({'width':'10%'})
        $(".page1-star1").css({'width':'15%'})
        var t=setTimeout(function(){
          $(".page1-word2").css({"transform":"rotate(-360deg)",'width':'80%',"left":"10%"})
        },1000)
        var t=setTimeout(function(){
          $(".page1-word3").css({"top":"75%"})
          $(".page1-word4").css({"top":"88%"})
        },2000)
        var t=setTimeout(function(){
          $(".page11-caihong").css({"left":"-5px"})
          $(".page1-people2").css({"left":"5%"})
          $(".page1-people1").css({"right":"3%"})
        },4000)
        var t=setTimeout(function(){
          $(".page1-qiqiu1").css({"top":"33%"})
          $(".page1-qiqiu2").css({"top":"0%"})
          $(".page1-qiqiu3").css({"top":"39%"})
        },5000)
      }else if(this.page == 2){
        // 第二页动画
        $(".page2-img1").css({"top":"15%",'left':'0%'})
        $(".page2-caiqi").css({"top":"-10px"})
        
        var t=setTimeout(function(){
          $(".page2-img2").css({"top":"15%",'left':'0%'})
        },1000)
        var t=setTimeout(function(){
          $(".page2-img3").css({"top":"15%",'left':'0%'})
        },2000)
      }else if(this.page == 3){
          // 第3页动画
          $(".page3-img3").css({'left':'0'})
          $(".page3-word2").css({'left':'20px'})
          var t=setTimeout(function(){
            $(".page3-img4").css({'left':'0'})
            $(".page3-word4").css({'right':'20px'})
          },1000)
          var t=setTimeout(function(){
            $(".page3-img5").css({'left':'0'})
            $(".page3-word3").css({'left':'20px'})
          },2000)
      }else if(this.page == 4){
        // 第四页动画
        var t=setTimeout(function(){
          $(".page3-img6").css({'top':'0%'})
          $(".page3-img7").css({'bottom':'0%'})
        },100)
        var t=setTimeout(function(){
           $(".page3-word5").css({'left':'50%'})
        },1100)

      }else if(this.page == 5){
        // 第5页动画
        var t=setTimeout(function(){
          $(".page3-img8").css({'left':'0'})
          $(".page3-word6").css({'left':'20px'})
        },100)
        var t=setTimeout(function(){
          $(".page3-img9").css({'left':'0'})
          $(".page3-word7").css({'right':'20px'})
        },1100)
        var t=setTimeout(function(){
          $(".page3-img10").css({'left':'0'})
          $(".page3-word8").css({'left':'20px'})
        },2100)

      }else if(this.page == 6){
        // 第6页动画
        var t=setTimeout(function(){
          $(".page3-img11").css({'top':'0'})
        },100)
        var t=setTimeout(function(){
          $(".page3-img12").css({'bottom':'0'})
        },1100)
        var t=setTimeout(function(){
          $(".page3-word9").css({'right':'20px'})
        },2100)
        var t=setTimeout(function(){
        },3100)
      }
      
    },
    guanbi(){
      $(".allmap").css("right","-100%")
    },
    daohang(){
   
      $(".allmap").css("right","0")
    },
    touchStart(e) {
      this.jishu ++;
      if(this.jishu == 1 ){
        this.bofang()
      }
      if(e.target.className == "daohang"){
        this.daohang()
      }
      if(e.target.className == "guanbi"){
        this.guanbi()
      }
      const touch = e.touches[0]
      this.touch.startX = touch.pageX
      this.touch.startY = touch.pageY
    },
    touchMove(e) {
      const touch = e.touches[0]
      const deltaX = touch.pageX - this.touch.startX
      const deltaY = touch.pageY - this.touch.startY
      this.panduan = deltaY
    },
    touchEnd(a) {
      
      if(this.panduan > 5){
        if(a==2){
          $("#page1").css("top",'0%')
          $("#page2").css("top",'100%')
          $("#page3").css("top",'200%')
          $("#page4").css("top",'300%')
          $("#page5").css("top",'400%')
          $("#page6").css("top",'500%')
          $("#page7").css("top",'600%')
          this.page = 1
        }else if(a == 3){
          $("#page1").css("top",'-100%')
          $("#page2").css("top",'0%')
          $("#page3").css("top",'100%')
          $("#page4").css("top",'200%')
          $("#page5").css("top",'300%')
          $("#page6").css("top",'400%')
          $("#page7").css("top",'500%')
          this.page = 2
        }else if(a == 4){
          $("#page1").css("top",'-200%')
          $("#page2").css("top",'-100%')
          $("#page3").css("top",'0%')
          $("#page4").css("top",'100%')
          $("#page5").css("top",'200%')
          $("#page6").css("top",'300%')
          $("#page7").css("top",'400%')
          this.page = 3
        }else if(a == 5){
          $("#page1").css("top",'-300%')
          $("#page2").css("top",'-200%')
          $("#page3").css("top",'-100%')
          $("#page4").css("top",'0%')
          $("#page5").css("top",'100%')
          $("#page6").css("top",'200%')
          $("#page7").css("top",'300%')
          this.page = 4
        }else if(a == 6){
          $("#page1").css("top",'-400%')
          $("#page2").css("top",'-300%')
          $("#page3").css("top",'-200%')
          $("#page4").css("top",'-100%')
          $("#page5").css("top",'0%')
          $("#page6").css("top",'100%')
          $("#page7").css("top",'200%')
          this.page = 5
        }else if(a == 7){
          $("#page1").css("top",'-500%')
          $("#page2").css("top",'-400%')
          $("#page3").css("top",'-300%')
          $("#page4").css("top",'-200%')
          $("#page5").css("top",'-100%')
          $("#page6").css("top",'0%')
          $("#page7").css("top",'100%')
          this.page = 6
        }
      }else if(this.panduan < -5){
        if(a == 1){
          $("#page1").css("top",'-100%')
          $("#page2").css("top",'0%')
          $("#page3").css("top",'100%')
          $("#page4").css("top",'200%')
          $("#page5").css("top",'300%')
          $("#page6").css("top",'400%')
          $("#page7").css("top",'500%')
          this.page = 2
        }else if( a==2 ){
          $("#page1").css("top",'-200%')
          $("#page2").css("top",'-100%')
          $("#page3").css("top",'0%')
          $("#page4").css("top",'100%')
          $("#page5").css("top",'200%')
          $("#page6").css("top",'300%')
          $("#page7").css("top",'400%')
          this.page = 3
        }else if(a == 3){
          $("#page1").css("top",'-300%')
          $("#page2").css("top",'-200%')
          $("#page3").css("top",'-100%')
          $("#page4").css("top",'0%')
          $("#page5").css("top",'100%')
          $("#page6").css("top",'200%')
          $("#page7").css("top",'300%')
          this.page = 4
        }else if(a == 4){
          $("#page1").css("top",'-400%')
          $("#page2").css("top",'-300%')
          $("#page3").css("top",'-200%')
          $("#page4").css("top",'-100%')
          $("#page5").css("top",'0%')
          $("#page6").css("top",'100%')
          $("#page7").css("top",'200%')
          this.page = 5
        }else if(a == 5){
          $("#page1").css("top",'-500%')
          $("#page2").css("top",'-400%')
          $("#page3").css("top",'-300%')
          $("#page4").css("top",'-200%')
          $("#page5").css("top",'-100%')
          $("#page6").css("top",'0%')
          $("#page7").css("top",'100%')
          this.page = 6
        }else if(a == 6){
          $("#page1").css("top",'-600%')
          $("#page2").css("top",'-500%')
          $("#page3").css("top",'-400%')
          $("#page4").css("top",'-300%')
          $("#page5").css("top",'-200%')
          $("#page6").css("top",'-100%')
          $("#page7").css("top",'0%')
          this.page = 7
        }
        
      }else{
      }
      this.panduan = 0
    },
    // 所有动画效果复原
    fuyuan(){
      // page1
      $('.page1-top').css("top","-100px")
      $(".page1-head").css({"height":"0","width":"0",'margin-left':"0"})
      $(".page1-word2").css({"transform":"rotate(0deg)",'width':'0%',"left":"50%",})
      $(".page1-word3").css({"top":"100%",})
      $(".page1-word4").css({"top":"100%",})
      $(".page11-caihong").css({"left":"-140px"})
      $(".page1-people2").css({"left":"20%"})
      $(".page1-people1").css({"right":"20%"})
      $(".page1-qiqiu1").css({"top":"100%"})
      $(".page1-qiqiu2").css({"top":"100%"})
      $(".page1-qiqiu3").css({"top":"100%"})
      // page2
      $(".page2-img1").css({"top":"120%",'left':'0%'})
      $(".page2-img2").css({"top":"-20%",'left':'-100%'})
      $(".page2-img3").css({"top":"120%",'left':'200%'})
      $(".page2-caiqi").css({"top":"-100%"})
      // page3
      $(".page3-img3").css({'left':'-100%'})
      $(".page3-img4").css({'left':'100%'})
      $(".page3-img5").css({'left':'-100%'})
      $(".page3-word2").css({'left':'-80px'})
      $(".page3-word4").css({'right':'-80px'})
      $(".page3-word3").css({'left':'-80px'})
      $(".page3-img6").css({'top':'-100%'})
      $(".page3-img7").css({'bottom':'-100%'})
      $(".page3-word5").css({'left':'-150%'})
      $(".page3-img8").css({'left':'-100%'})
      $(".page3-img9").css({'left':'100%'})
      $(".page3-img10").css({'left':'-100%'})
      $(".page3-word6").css({'left':'-80px'})
      $(".page3-word7").css({'right':'-80px'})
      $(".page3-word8").css({'left':'-80px'})
      $(".page3-img11").css({'top':'-100%'})
      $(".page3-img12").css({'bottom':'-100%'})
      $(".page3-word9").css({'right':'-80px'})
      
      
    },

  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.body-width{height: 100%;width:100%;left: 0;position: absolute;overflow: hidden;top:0;}
#page1{top:0;transition:all 1s ease;}
#page2{background: url(../assets/page2-bg.jpg) no-repeat center center;top:100%;transition:all 1s ease;-webkit-background-size: 100% 100%;
background-size: 100% 100%;}
#page3{top:200%;transition:all 1s ease;background-color: #fff;}
#page4{top:300%;transition:all 1s ease;background-color: #fff;}
#page5{top:400%;transition:all 1s ease;background-color: #fff;}
#page6{top:500%;transition:all 1s ease;background-color: #fff;}

#page7{background: url(../assets/page4-bg.png) no-repeat center center;top:600%;transition:all 1s ease;-webkit-background-size: 100% 100%;
background-size: 100% 100%;}

.tiao{background-color: #9AE1FA;height:100%;width:100%;margin:0;display: flex;justify-content: center;align-items: center;}
.zhi{position: relative;}
.zhi:after{content: "";height: 8px;width: 50px;background-color: #000;opacity: 0.2;position: absolute;border-radius: 50%;top:40px;left:-20px;animation: shadow 0.5s infinite linear;}
.zhi:before{content: "";height: 50px;width: 50px;background-color: #fff;opacity: 0.9;position: absolute;border-radius: 5px;top:-40px;left:-20px;animation: zhuanShow 0.5s infinite linear;}
@keyframes shadow{
  0%{transform: scale(1);}
  50%{transform: scale(1.2);}
  100%{transform: scale(1);}
}
@keyframes zhuanShow{
  0%{transform: translateY(0) rotate(0deg);}
  25%{transform: translateY(10px) rotate(22.5deg);}
  50%{transform:translateY(30px) rotate(45deg) scale(1.1,0.9);border-bottom-right-radius:50px;}
  75%{transform: translateY(10px) rotate(67.5deg) ;}100%{transform:translateY(0) rotate(90deg) ;}
}
.jiazai{position: absolute;top:60%;color:#fff;font-size: 20px;}
.jiazai-animate{z-index:10;}
.sky {
  height: 100%;
/*  background: #5DADD7;
*/  position: relative;
  overflow: hidden;
  -webkit-animation: sky_background 50s ease-out infinite;
  animation: sky_background 50s ease-out infinite;
  -o-animation: sky_background 50s ease-out infinite;
  animation: sky_background 50s ease-out infinite;
  -webkit-transform: translate3d(0, 0, 0);
  -ms-transform: translate3d(0, 0, 0);
  -o-transform: translate3d(0, 0, 0);
  transform: translate3d(0, 0, 0);
}
@-webkit-keyframes sky_background {0% {/*background: #007fd5;*/color: #007fd5;}50% {/*background: #000;*/color: #a3d9ff;}100% {/*background: #007fd5;*/color: #007fd5;}}
@keyframes sky_background {0% {/*background: #007fd5;*/color: #007fd5;}50% {/*background: #000;*/color: #a3d9ff;}100% {/*background: #007fd5;*/color: #007fd5;}}
@-webkit-keyframes cloud_one {0% {left: 0;}100% {left: -200%;}}
@keyframes cloud_one {0% {left: 0;}100% {left: -200%;}}
@-webkit-keyframes cloud_two {0% {left: 0;}100% {left: -200%;}}
@keyframes cloud_two {0% {left: 0;}100% {left: -200%;}}
@-webkit-keyframes cloud_three {0% {left: 0;}100% {left: -200%;}}
@keyframes cloud_three {0% {left: 0;}100% {left: -200%;}}
.sky .clouds_three { 
  background: url(../assets/cloud_one.png) no-repeat;
  position: absolute;
  left: 0;
  top: 50%;
  height: 100%;
  width: 300%;
  -webkit-animation: cloud_three 100s linear infinite;
  animation: cloud_three 100s linear infinite;
  -o-animation: cloud_three 100s linear infinite;
  animation: cloud_three 100s linear infinite;
  -webkit-transform: translate3d(0, 0, 0);
  -ms-transform: translate3d(0, 0, 0);
  -o-transform: translate3d(0, 0, 0);
  transform: translate3d(0, 0, 0);
}
.sky .clouds_two {
  background: url(../assets/cloud_two.png) no-repeat;
 position: absolute;
  left: 0;
  top: 50%;
  height: 100%;
  width: 300%;
  -webkit-animation: cloud_two 75s linear infinite;
  animation: cloud_two 75s linear infinite;
  -o-animation: cloud_two 75s linear infinite;
  animation: cloud_two 75s linear infinite;
  -webkit-transform: translate3d(0, 0, 0);
  -ms-transform: translate3d(0, 0, 0);
  -o-transform: translate3d(0, 0, 0);
  transform: translate3d(0, 0, 0);
}
.sky .clouds_one {
  background: url(../assets/cloud_three.png) no-repeat;
  position: absolute;
  left: 0;
  top: 50%;
  height: 100%;
  width: 300%;
  -webkit-animation: cloud_one 50s linear infinite;
  animation: cloud_one 50s linear infinite;
  -o-animation: cloud_one 50s linear infinite;
  animation: cloud_one 50s linear infinite;
  -webkit-transform: translate3d(0, 0, 0);
  -ms-transform: translate3d(0, 0, 0);
  -o-transform: translate3d(0, 0, 0);
  transform: translate3d(0, 0, 0);
}
.page1-head{width: 0;height: 0;border-radius: 50%;position: absolute;top:16.5%;z-index: 10;left:50%;margin-left: 0;transition:all 3s ease;}
.page1-head img{width: 100%;height: 100%;}
.page1-top{position: absolute;top:-100px;z-index: 2;width:100%;transition:all 3s ease;}
.page1-top img{width: 100%;}
.shanghua{position: fixed;bottom: 0px;z-index: 999;width: 100%;height:50px;background:url(../assets/up.png) no-repeat center center;animation: touming 1s ease-in infinite alternate;
  -webkit-animation: touming 1s ease-in infinite alternate;}
@keyframes touming{
  from {opacity: 1;}
  to {opacity: 0;}
}
.xiahua{position: fixed;top: 0px;z-index: 999;width: 100%;height:50px;background:url(../assets/down.png) no-repeat center center;animation: touming 1s ease-in infinite alternate;
  -webkit-animation: touming 1s ease-in infinite alternate;}
.music{}
.page1-cloud1{position: absolute;z-index: 5;top:25%;width:28%;left:-30px;}
.page1-cloud2{position: absolute;z-index: 5;top:30%;width:35%;left:60%;}
.page1-word1{position: absolute;top:45%;background: url(../assets/page1-word1.png) no-repeat center center;z-index: 5;width:100%;height: 38px;-webkit-background-size: 40% 70%;
background-size: 40% 70%;}
.page11-caihong{position: absolute;z-index: 6;top:49%;height: 100px;width: 140px;left:-140px;transition:all 2s ease;}
.page1-word2{position: absolute;z-index: 5;width: 0%;top:53%;left:50%;transition:all 3s ease;}
.page1-word3{position: absolute;z-index: 5;width: 90%;top:100%;left:5%;transition:all 3s ease;}
.page1-word4{position: absolute;z-index: 6;width: 70%;top:100%;left:20%;transition:all 3s ease;}
.page1-word5{position: absolute;z-index: 5;width: 90%;top:86%;left:5%;}
.page1-star2{position: absolute;z-index: 5;width: 10%;top:64%;left:2%;animation: bigToSmallTwo 1s ease-in infinite alternate;
  -webkit-animation: bigToSmallTwo 1s ease-in infinite alternate;}
.page1-star1{position: absolute;z-index: 5;width: 15%;top:65%;right:1%;animation: bigToSmall 1s ease-in infinite alternate;
  -webkit-animation: bigToSmall 1s ease-in infinite alternate;}
.page1-qiqiu1{position: absolute;z-index: 5;width: 15%;top:100%;left:0;transition:all 5s ease;}
.page1-qiqiu2{position: absolute;z-index: 5;width: 15%;top:100%;right:0;transition:all 5s ease;}
.page1-qiqiu3{position: absolute;z-index: 5;width: 10%;top:100%;right:0%;transition:all 5s ease;}
.page1-people1{position: absolute;z-index: 4;width: 15%;top:51%;right:-20%;transition:all 2s ease;}
.page1-people2{position: absolute;z-index: 6;width: 15%;top:83%;left:-20%;transition:all 2s ease;}
.page2-yijia{width: 100%;position: absolute;top:20px;z-index: 6;}
.page2-yijianei{width:80%;height: 65%;border:2px solid #000;position: absolute;top:30%;left: 10%;overflow: hidden;}
.page2-word{position: absolute;top:20px;left: 20px;width: 30%;}
.page2-sun{position: absolute;top:20px;right: 20px;width: 20%;animation: zhuanSun 1s ease-in infinite alternate;
  -webkit-animation: zhuanSun 1s linear infinite alternate;}
.page2-img1{position: absolute;width: 100%;left: 0%;z-index: 5;transition: all 1s ease;transform: rotate(0deg);top:120%;}
.page2-img2{position: absolute;width: 100%;left: -100%;z-index: 6;transition: all 1s ease;transform: rotate(0deg);top:-20%;}
.page2-img3{position: absolute;width: 100%;left: 200%;z-index: 7;transition: all 1s ease;transform: rotate(0deg);top:120%;}
.page2-caiqi{position: absolute;top:-100%;width: 100%;transition: all 1s ease;}
.page2-qiqiu2{position: absolute;left:5px;top:30%;z-index: 8;width: 50px;}
.page2-qiqiu1{position: absolute;right:5px;top:70%;z-index: 8;width: 50px;}
.page2-hengxian{position: absolute;width: 80%;left: 2.5%;top:89%;}
.page3-img3,.page3-img4,.page3-img5{position: absolute;width: 100%;height: 33%;transition: all 1s ease;}
.page3-img3{top:0;left:-100%;}
.page3-img4{top:34%;left:100%;}
.page3-img5{top:68%;left:-100%;}
.page3-img8,.page3-img9,.page3-img10{position: absolute;width: 100%;height: 33%;transition: all 1s ease;}
.page3-img8{top:0;left:-100%;}
.page3-img9{top:34%;left:100%;}
.page3-img10{top:68%;left:-100%;}
.page3-word2,.page3-word3,.page3-word4{position: absolute;width: 15%;transition: all 1s ease;animation: bigToSmall 0.5s ease-in infinite alternate;-webkit-animation: bigToSmall 0.5s linear infinite alternate;}
.page3-word2{top:20%;left: -80px;}
.page3-word4{top:50%;right: -80px;}
.page3-word3{top:80%;left: -80px;}
.page3-word6,.page3-word8,.page3-word7{position: absolute;width: 15%;transition: all 1s ease;animation: bigToSmall 0.5s ease-in infinite alternate;-webkit-animation: bigToSmall 0.5s linear infinite alternate;}
.page3-word6{top:20%;left: -80px;}
.page3-word7{top:50%;right: -80px;}
.page3-word8{top:80%;left: -80px;}
.page3-img6,.page3-img7{position: absolute;transition: all 1s ease;width:100%;}
.page3-img6{top:-100%;}
.page3-img7{bottom: -100%;}
.page3-imgfff{position: absolute;width: 100%;height: 100%;transition: all 0.5s ease;background-color: #fff;opacity: 0;}
.page3-imgfff1{position: absolute;width: 100%;height: 100%;transition: all 0.5s ease;background-color: #fff;opacity: 0;}
.page3-imgfff2{position: absolute;width: 100%;height: 100%;transition: all 0.5s ease;background-color: #fff;opacity: 0;}
.page3-word5{position: absolute;transition: all 1s ease;animation: zhuanWord 0.5s ease-in infinite alternate;-webkit-animation: zhuanWord 0.5s linear infinite alternate;top:45%;left: -150%;margin-left: -90px;width:180px;}
.page3-img11{position: absolute;transition: all 1s ease;top:-100%;width: 100%;height: 40%;}
.page3-img12{position: absolute;transition: all 1s ease;bottom:-100%;width: 100%;height: 60%;}
.page3-word9{transition: all 1s ease;position: absolute;right: -80px;top:50px;width: 15%;animation: zhuanWord 0.5s ease-in infinite alternate;-webkit-animation: zhuanWord 0.5s linear infinite alternate;}
.page1-caiqi{position: absolute;top:-10px;width: 100%;}
.page4-word1{position: absolute;transition: all 1s ease;top:110px;width: 60%;left:20%;}
.page4-word2{position: absolute;transition: all 1s ease;top:300px;width: 60%;left:20%;}
.daojishi{position: absolute;top:230px;width: 85%;background: url(../assets/page1-word5.png) no-repeat center center; -webkit-background-size: 100% 100%;height: 50px;left:10%;color:#fff;text-align: center;font-size: 18px;line-height: 50px;letter-spacing: 10px;font-weight: 800;font-family: "LiSu","YouYuan";
background-size: 100% 100%;}
.daohang{position: absolute;bottom:100px;width: 50px;left:50%;margin-left: -25px;}
.page4-bottom{position: absolute;width: 100%;bottom: 0;}


@keyframes bigToSmall{
  from {width: 15%;}
  to {width: 18%;;}
}
@keyframes zhuanSun{
  from {transform: rotate(0deg);width: 20%;}
  to {transform: rotate(360deg);width: 25%;}
}
@keyframes zhuanWord{
  from {transform: rotate(-5deg);}
  to {transform: rotate(5deg);}
}


@keyframes bigToSmallTwo{
  from {width: 13%;}
  to {width: 10%;}
}
.wrap {
  width: 300px;
  height: 300px;
}
.center {
  position: absolute;
  top: 30%;
  left: 50%;
  transform: translate(-50%, -50%);
}
.img1 {
  position: absolute;
  width: 100%;
  height: 100%;
  background: url(../assets/img1.png) no-repeat center center;
  -webkit-background-size: 100% 100%;
  background-size: 100% 100%;
}
.img2 {
  position: absolute;
  width: 100%;
  height: 100%;
  background: url(../assets/img2.png) no-repeat center center;
  -webkit-background-size: 100% 100%;
  background-size: 100% 100%;
}
.img3 {
  position: absolute;
  width: 100%;
  height: 100%;
  background: url(../assets/img3.png) no-repeat center center;
  -webkit-background-size: 100% 100%;
  background-size: 100% 100%;
}
.move1 {
  animation: myMove1 5s ease-in infinite alternate;
  -webkit-animation: myMove1 5s ease-in infinite alternate;
}
.move2 {
  animation: myMove2 3s ease infinite alternate;
  -webkit-animation: myMove1 3s ease infinite alternate;
}
.move3 {
  animation: myMove3 2s ease-in infinite alternate;
  -webkit-animation: myMove1 2s ease-in infinite alternate;
}
@keyframes myMove1 {
  from {transform: rotate(0deg);}
  to {transform: rotate(360deg);}
}
@-webkit-keyframes myMove1 {
  from {transform: rotate(0deg);}
  to {transform: rotate(360deg);}
}
@keyframes myMove2 {
  from {transform: rotate(0deg);}
  to {transform: rotate(360deg);}
}
@-webkit-keyframes myMove2 {
  from {transform: rotate(0deg);}
  to {transform: rotate(360deg);}
}
@keyframes myMove3 {
  from {transform: rotate(0deg);}
  to {transform: rotate(360deg);}
}
@-webkit-keyframes myMove3 {
  from {transform: rotate(0deg);}
  to {transform: rotate(360deg);}
}
.cloud{
  position: absolute;
  top:150px;
  left: 500px;
  height: 40px;
  width: 150px;
/*  background-color: #fff;
*/  border-radius: 20px;
  
}
.cloudA{
  top:10%;
  left:-100px;
  transform: scale(0.8);
  animation:cloud 5s infinite ease;/*ease缓动 先加速后减速*/
}
.cloudA img{width:90%;}
.cloud-1{
    position: absolute;
    left: 20px;
    top:-10px;
    border-radius:50%;
    height: 50px;
    width: 50px;
    background-color: #fff;
    z-index: 5;
  }
  .cloud-2{
    position: absolute;
    left: 60px;
    top:-30px;
    border-radius:50%;
    height: 60px;
    width: 70px;
    background-color: #fff;
  }
@keyframes cloud{
  0%{transform: translateX(0%) scale(0.8);}
  100%{transform: translateX(320%) scale(0.8);}
}

#audio_btn {
    display: inline-block;
    position: fixed;
    left: 20px;
    top: 70px;
    width: 30px;
    height: 30px;
    
    z-index: 99999;
}
.moren-rotate{
  background-image: url(../assets/zanting.png);
  background-size: contain;
}
.rotate {
    -webkit-animation: rotating 1.2s linear infinite;
    -moz-animation: rotating 1.2s linear infinite;
    -o-animation: rotating 1.2s linear infinite;
    animation: rotating 1.2s linear infinite;
    background-image: url(../assets/play.png);
    background-size: contain;
}

@-webkit-keyframes rotating {
    from { -webkit-transform: rotate(0) }
    to { -webkit-transform: rotate(360deg) }
}

@keyframes rotating {
    from { transform: rotate(0) }
    to { transform: rotate(360deg) }
}
@-moz-keyframes rotating {
    from { -moz-transform: rotate(0) }
    to { -moz-transform: rotate(360deg) }
}
</style>
