<template>
  <div class="icons-wrapper" >
    <swiper :options="swiperOption">
      <swiper-slide>
        <div class="icon"  v-for="item1 of icons1" :key = "item1.id">
          <div class="icon-img">
            <img :src="item1.imgUrl" class="img-content" alt="">
          </div>
          <p class="icon-des">{{item1.des}}</p>
        </div>
      </swiper-slide>
      <swiper-slide>
         <div class="icon"  v-for="item2 of icons2" :key="item2.id">
            <div class="icon-img">
              <img :src="item2.imgUrl" class="img-content" alt="">
            </div>
            <p class="icon-des">{{item2.des}}</p>
         </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: "HomeIcons",
  props:{ 
      icons1:{
        type:Array
      },
      icons2:{
        type:Array
    }
  },
  data () {
    return {
      swiperOption:{
        autoplay:false
      }
    }
  }
}
    //   iconsList1: [
    //     {
    //       id:1,
    //       imgUrl:
    //         "http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png",
    //       des: "景点门票"
    //     },
    //     {
    //       id:2,
    //       imgUrl:
    //         "http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png",
    //       des: "北京必游"
    //     },
    //     {
    //       id:3,          
    //       imgUrl:
    //         "http://img1.qunarzz.com/piao/fusion/1803/96/c70f1e85ae4a4f02.png",
    //       des: "自然风光"
    //     },
    //     {
    //       id:4,
    //       imgUrl:
    //         "http://img1.qunarzz.com/piao/fusion/1803/20/831d62d2e1c7be02.png",
    //       des: "文化古迹"
    //     },
    //     {
    //       id:5,
    //       imgUrl:
    //         "http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png",
    //       des: "动植物园"
    //     },
    //     {
    //       id:6,
    //       imgUrl:
    //         "http://img1.qunarzz.com/piao/fusion/1803/6c/9e54a8540fee0102.png",
    //       des: "故宫"
    //     },
    //     {
    //       id:7,
    //       imgUrl:
    //         "http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png",
    //       des: "一日游"
    //     },
    //     {
    //       id:8,
    //       imgUrl:
    //         "http://img1.qunarzz.com/piao/fusion/1803/ab/6f7d6e44963c9302.png",
    //       des: "泡温泉"
    //     }
    //   ],
    //   iconsList2: [
    //     {
    //       id:9,
    //       imgUrl:"http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png",
    //       des: "游乐场"
    //     },
    //     {
    //       id:10,
    //       imgUrl:"http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png",
    //      des: "全部玩乐"
    //     }
    //   ]
    // };
  

</script>

<style scoped lang="stylus">
  @import '../../../assets/styles/varibles.styl'
.icons-wrapper 
  overflow: hidden;
  height: 0;
  padding-bottom: 50%;
  margin-top .1rem
  // background: #eeffee;
  .icon 
    float: left;
    position: relative;
    overflow: hidden;
    width: 25%;
    height: 0;
    padding-bottom: 25%;
    .icon-img 
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0.44rem;
      box-sizing: border-box;
      padding: 0.1rem;
      .img-content 
        display: block;
        margin: 0 auto;
        height: 100%;
    .icon-des
      position absolute
      bottom 0
      right 0
      left 0
      line-height .44rem
      height .44rem
      text-align center
      color $fontColor
      overflow hidden
      white-space nowrap
      text-overflow ellipsis
</style>