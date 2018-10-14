<template>
    <div>
        <div class="banner"  @click="handleBannerClick">                   
            <img class="banner-img" :src="bannerImg" alt="北京欢乐谷">
            <div class="banner-info">
                <div class="banner-pic">
                    <div class="banner-wrapper">
                        <span class="iconfont pic">&#xe616;</span>
                        <span class="banner-number">16</span>
                    </div>
                </div>
                <div class="banner-title">{{bannerTitle}}</div>
            </div>
        </div>
        <fade-animation>
        <common-gallary 
        :imgs="gallaryImgs" 
        v-show="showGallary"
        @close="gallaryClose"
        ></common-gallary>
        </fade-animation>
    </div>
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/FadeAnimation'
export default {
    name:"DetailBanner",
    props:{
        bannerImg:String,
        gallaryImgs:Array,
        bannerTitle:String
    },
    data () {
        return {
            showGallary:false
            
            }
    },
    methods: {
         handleBannerClick () {
             this.showGallary = true
         },
         gallaryClose () {
             this.showGallary = false
         }
      
    },
    components:{
        CommonGallary,
        FadeAnimation
    },
}
</script>

<style scoped lang="stylus">
    .banner
        overflow hidden
        height 0
        padding-bottom 55%
        position relative
        &:after
            content: " ";
            display: block;
            position: absolute;
            bottom: 0;
            left: 0;
            width: 100%;
            min-height: .6rem;
            background-color: transparent;
            background-image: linear-gradient(to bottom,rgba(0,0,0,0),rgba(0,0,0,.8)); 

        .banner-img
            width 100%
        .banner-info
            color #fff
            position: absolute;
            right: 3.2rem;
            bottom: .36rem;
            left: .2rem;
            min-height: .4rem;
            .banner-pic
                width 1.2rem
                background rgba(0,0,0,.5)
                margin-bottom .16rem
                margin-left .1rem
                border-radius .2rem
                text-align center
                .pic
                    font-size .16rem
                    line-height .36rem
                .banner-number
                    vertical-align center
                    font-size .16rem 
                    padding .04rem               
            .banner-title
                font-size .36rem
                line-height .4rem
                z-index 1
                text-shadow: 0 1px 2px rgba(0,0,0,0.70)
</style>