<template>
    <div class="header">
        <h1>城市选择</h1>
        <router-link to="/">
            <div class="iconfont city-back">&#xe624;</div>
        </router-link>
    </div>
</template>

<script>
export default {
    name:"CityHeader"
}
</script>

<style lang="stylus" scoped>
@import "../../../assets/styles/varibles.styl"
    .header
        background $bgColor
        font-size .32rem
        color #ffffff
        text-align center
        line-height .86rem
        height .86rem
        position relative
        .city-back
            position absolute 
            font-size .4rem
            top 0
            left .1rem
            color #fff
</style>