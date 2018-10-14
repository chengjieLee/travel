<template>
    <div>
        <div class="recommend-title">猜你喜欢</div>
        <ul>
            <router-link tag="li" 
                        class="item border-bottom" 
                        v-for ="item of recommend" 
                        :key = "item.id" 
                        :to = "'/detail/' + item.id">
                <img :src="item.imgUrl" class="item-img">   
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <div>
                    <span class="evaluate">★★★★★</span>
                    <span class="item-des">{{item.des}}</span>
                    </div>
                    <button class="item-button">查看详情</button>
                </div>
            </router-link>
        </ul>
        <div class="recommend-footer">
            <a href="#">产看所有产品</a>
        </div>
    </div>
</template>

<script>
export default {
  name: "HomeRecommend",
  props:{
      recommend:Array
  }
//   data () {
//       return {
//           picList:[
//              {
//                   id:0,
//                   title: '北京欢乐谷',
//                   des:'59929条评论',
//                   imgUrl:"http://img1.qunarzz.com/sight/p0/1508/89/895a1b7add84f23faca053ce9e3153db.water.jpg_200x200_99ae30ee.jpg"
//               },
//              {
//                   id:1,
//                   title: '故宫',
//                   des:'39929条评论',
//                   imgUrl:"http://img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_200x200_1bc99086.jpg"
//               },
//                {
//                   id:2,
//                   title: '北京野生动物园',
//                   des:'12929条评论',
//                   imgUrl:"http://img1.qunarzz.com/sight/p0/1507/36/ce3d2d6c9ab44d67ae68d940b8781829.water.jpg_200x200_0938a8f2.jpg"
//               },
//                {
//                   id:3,
//                   title: '世界公园',
//                   des:'11929条评论',
//                   imgUrl:"http://img1.qunarzz.com/sight/p0/1508/2f/e615bc3c8e0cf46d9fb92c58ac305f45.water.jpg_200x200_e4e69a48.jpg"
//               },
//                {
//                   id:4,
//                   title: '古北水镇',
//                   des:'11929条评论',
//                   imgUrl:"http://img1.qunarzz.com/sight/p0/1804/c8/c88bb5e69c9a9c5ea3.img.jpg_200x200_740720ff.jpg"
//               },
//                {
//                   id:5,
//                   title: '圆明园',
//                   des:'11929条评论',
//                   imgUrl:"http://img1.qunarzz.com/sight/p0/1505/f5/f5f45e1a83537bcb.water.jpg_200x200_444cc7e8.jpg"
//               },
//                {
//                   id:6,
//                   title: '北京海洋馆',
//                   des:'11929条评论',
//                   imgUrl:"http://img1.qunarzz.com/sight/p0/1602/68/68aa05adb5315f9990.water.jpg_200x200_ce3d2658.jpg"
//               },
//           ],
//       }
//   }
};
</script>

<style scoped lang="stylus">
.recommend-title 
    background: #eeffee;
    line-height: 0.8rem;
    text-indent: 0.3rem;
    margin-top: 0.1rem;
.item 
    display: flex;
    overflow: hidden;
    height: 1.9rem;
    .item-img
        width 1.7rem
        height 1.7rem
        padding .1rem
    .item-info
        flex 1
        padding .1rem
        min-width 0
        .evaluate
            font-size .3rem
            color:#ffb436
        .item-title
            line-height .54rem
            font-size .32rem
        .item-des
             line-height .4rem
             color:#bbb
             overflow hidden
             white-space nowrap
             text-overflow ellipsis
        .item-button
            line-height .42rem
            margin-top .3rem
            margin-left 1.1rem
            background #ff9300
            padding  0 .2rem
            border-radius .07rem
            color #fff
            border-style none
.recommend-footer
        text-align center
        a
            display inline-block
            color #00afc7
            padding .2rem 0
            font-size .3rem
</style>

