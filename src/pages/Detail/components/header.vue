<template>
    <div class="detail-header">
         <router-link :to="'/'">
            <div 
            v-show="!headerShow"
            class="iconfont back-icon">&#xe624;</div>
        </router-link>
        <div class="header-fixed"
             v-show="headerShow"
             :style="opacityStyle"
             >
            <h1>景点详情</h1>
            <router-link to="/">
                <div class="iconfont city-back">&#xe624;</div>
            </router-link>
        </div>
    </div>
</template>

<script>

export default {
    name:"DetailHeader",
    data () {
        return {
            headerShow: false,
            opacityStyle:{
                opacity: 0
            }
        }
    },
    methods:{
        handleScroll () {
            const top = document.documentElement.scrollTop
           if( top > 50){
               if(top<140){
               let opacity = top/140 
               opacity = opacity > 1 ? 1: opacity
               this.opacityStyle = { opacity }
               }  
               this.headerShow = true
           } else {
               this.headerShow = false
           }
        }
    },
    activated () {
        window.addEventListener('scroll',this.handleScroll)
    },
    deactivated () {
        window.removeEventListener('scroll',this.handleScroll)
    }
}
</script>

<style scoped lang="stylus">
@import "../../../assets/styles/varibles.styl"
    .detail-header
        .back-icon
            position absolute
            top .2rem
            left .2rem
            background-color rgba(0,0,0,.5)
            border-radius 50%
            padding .16rem
            color #fff
            font-weight bolder
            font-size .36rem
         .header-fixed
            z-index 2
            background $bgColor
            font-size .32rem
            color #ffffff
            text-align center
            line-height .86rem
            height .86rem
            position fixed
            top 0
            left 0 
            right 0
            width 100%
            .city-back
                position fixed
                font-size .4rem
                top 0
                left .1rem
                color #fff
</style>