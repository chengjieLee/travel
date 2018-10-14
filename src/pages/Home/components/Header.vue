<template>
<div class="header">
   <div class="header-left">
       <div class="iconfont back-icon">&#xe624;</div>
   </div>
   <div class="header-input">
       <span class="iconfont">&#xe632;</span>
       输入城市，景区，游玩主题
   </div>
   <router-link to='/city'>
        <div class="header-right">{{this.city}}<span class="iconfont arrow-down">&#xe6aa;</span>
       </div>
   </router-link>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
      ...mapState(['city'])
  }
}
</script>


<style scoped lang="stylus">
    @import '../../../assets/styles/varibles.styl'
    .header
        display:flex
        line-height: .86rem
        background:$bgColor
        color:#fff
        .header-left
            width: .64rem
            float:left
            .back-icon
                font-size:0.4rem
                text-align:center
        .header-input
            flex:1
            height:.64rem
            margin-top:.12rem
            margin-left:.12rem
            background:#fff
            border-radius:.1rem
            color:#ccc
            line-height:0.64rem
            padding-left:0.12rem
        .header-right
            width 1.24rem
            float:right
            text-align:center
            color #fff
            white-space nowrap
            overflow hidden
            .arrow-down
               font-size:.3rem  
</style>