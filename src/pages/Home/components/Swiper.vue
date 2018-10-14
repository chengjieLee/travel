<template>
<div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of list" :key="item.id"> 
          <img class="swiper-img" :src="item.imgUrl">
      </swiper-slide>

    <div class="swiper-pagination"  slot="pagination"></div>
    <div class="swiper-scrollbar"   slot="scrollbar"></div>
  </swiper>

</div>

</template>

<script>
export default {
  name: "HomeSwiper",
  props:{
    list:Array
  },
  data () {
    return {
      swiperOption: {
        pagination:'.swiper-pagination',
        loop:true,
        autoplay: 1400,
        speed: 600
      },
      // swiperList: [{
      //   id:'0001',
      //   imgUrl:'http://img1.qunarzz.com/piao/fusion/1809/9b/8f79dbd1e0941302.jpg_750x200_55829659.jpg'
      // },
      // {
      //   id:'0002',
      //   imgUrl:'http://img1.qunarzz.com/piao/fusion/1809/a1/fa9b75fda7bc902.jpg_750x200_bd73e932.jpg'
      // },
      // {
      //   id:'0003',
      //   imgUrl:'http://img1.qunarzz.com/piao/fusion/1808/70/5603e6a535062402.jpg_750x200_2c552f2c.jpg'
      // },
      // {
      //   id:'0004',
      //   imgUrl:'http://img1.qunarzz.com/piao/fusion/1807/66/e5a5cec881702f02.jpg_750x200_67bb5691.jpg'
      // }]
    }
  }
}
</script>


<style scoped lang="stylus">
.wrapper >>> .swiper-pagination-bullet-active
  background #fff
.wrapper
  width 100%
  height 0
  padding-bottom 26.7%
  overflow hidden
  .swiper-img
    width:100%
</style>