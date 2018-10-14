<template>
    <div>
        <detail-banner 
        :bannerImg="bannerImg" 
        :gallaryImgs="gallaryImgs"
        :bannerTitle="bannerTitle"
        ></detail-banner>
        <detail-header></detail-header>
        <detail-list :list="list"></detail-list>
        <div class="height"></div>
    </div>
</template>

<script>
import DetailBanner from './components/banner'
import DetailHeader from './components/header'
import DetailList from './components/list'
import axios from 'axios'
export default {
    name:"Detail",
    components:{
        DetailBanner,
        DetailHeader,
        DetailList
    },
    methods:{
         getDetailInfo () {
             axios.get('/api/detail.json',{
                 params: {
                     id: this.$route.params.id
                 }
             })
             .then(this.detailInfoSucc)
         },
         detailInfoSucc (res) {
            res = res.data           
            if(res.ret && res.data){
                let data = res.data
                const index = parseInt(this.$route.params.id)       
                data = data.detail[index]      
                this.list = data.categoryList
                this.bannerImg = data.bannerImg
                this.gallaryImgs = data.gallaryImgs
                this.bannerTitle = data.sightName
            }
         }
    },
    data () {
        return {
            list: [],
            gallaryImgs:[],
            bannerImg:"",
            bannerTitle:"",
        }
    },
    mounted () {
        this.getDetailInfo()
    }
}
</script>

<style scoped lang="stylus">
    .height
        height 20rem
</style>

