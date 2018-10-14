<template>
    <div class="container" @click="closeGallary">
        <div class="wrapper">
            <swiper :options="swiperOptions">
                <swiper-slide v-for="(item,index) of imgs" :key="index"> 
                    <img class="swiper-img" :src="item">
                </swiper-slide>
                <div class="swiper-pagination"  slot="pagination"></div>
            </swiper>
        </div>
    </div>
</template>

<script>
export default {
    name:"CommenGallary",
    props: {
        imgs:{
            type:Array
        }
    },
    methods:{
        closeGallary () {
            this.$emit('close')
        }
    },
    data () {
        return {
            swiperOptions:{
                pagination : ".swiper-pagination",
                paginationType: 'fraction',
                observeParents: true,
                observer: true //监听dom结构发生变化时自我刷新
            }
        }
    }
}
</script>

<style scoped lang="stylus">
    .container>>>.swiper-container
        overflow inherit
    .container
        display flex
        flex-direction column
        justify-content center
        position fixed
        left 0
        right  0
        bottom 0
        top 0
        background #000
        z-index 99
        .wrapper
            width 100%
            height 0 
            padding-bottom 100%
            .swiper-img
                width 100%
            .swiper-pagination
                color #ffffff
                bottom -1rem
</style>
