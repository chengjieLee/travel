<template>
<div>
    <home-header></home-header>
    <home-swiper :list="swiperList"></home-swiper>
    <home-icons :icons1="iconsList1" :icons2="iconsList2"></home-icons>
    <home-recommend :recommend="recommend"></home-recommend>
    <home-weekend :weekend ="weekend"></home-weekend>
  </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/Icons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'
import axios from 'axios'
import { mapState } from 'vuex'

export default {
  name: 'Home',
  components:{
    HomeHeader,
    HomeSwiper,
    HomeIcons,
    HomeRecommend,
    HomeWeekend
  },
  data () {
    return {
      lastCity:'',
      swiperList:[],
      iconsList1:[],
      iconsList2:[],
      recommend:[],
      weekend:[]
    }
  },
  computed: {
    ...mapState(['city'])
  },
  methods:{
    getHomeInfo () {
      axios.get('/api/data.json?city=' + this.city)
          .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc (res) {
      res = res.data
      if(res.ret&&res.data){
        const data = res.data
        this.swiperList= data.swiperList
        this.iconsList1 = data.iconsList1
        this.iconsList2 = data.iconsList2
        this.recommend = data.picList
        this.weekend = data.weekList
      }
    }
  },
  mounted () {
    this.lastCity = this.city
    this.getHomeInfo()
  },
  activated () {
    if(this.lastCity !== this.city){
      this.getHomeInfo()
      this.lastCity = this.city
    }
  }
}
</script>


<style scoped>

</style>