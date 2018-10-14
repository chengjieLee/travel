<template>
 <div class="weekend">
     <div class="weekend-header">周末去哪儿</div>
     <div class="weekend-content" v-for="item of weekend" :key="item.id">
        <img :src="item.imgUrl" class="weekend-img">
        <p class="weekend-title">{{item.title}}</p>
        <p class="weekend-des">{{item.des}}</p>
     </div>
 </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props:{
      weekend:Array
  }
//   data () {
//       return {
//           weekList:[
//               {
//                   id:1,
//                   imgUrl:'http://img1.qunarzz.com/sight/source/1606/85/c6b6bad1b977e.jpg_r_640x214_5c638941.jpg',
//                   title:'漂流涌进，烧烤陆营',
//                   des:'轻松水上漂，任我乐逍遥'
//               },
//                {
//                   id:2,
//                   imgUrl:'http://img1.qunarzz.com/sight/source/1505/53/02091f1ee43d0a.jpg_r_640x214_2e3256b1.jpg',
//                   title:'北京清凉避暑胜地',
//                   des:'到大自然中享受“天然空调”的清凉'
//               },
//               {
//                   id:3,
//                   imgUrl:'http://img1.qunarzz.com/sight/source/1505/aa/7baaf8a851d221.jpg_r_640x214_1431200f.jpg',
//                   title:'北京必游TOP10',
//                   des:'来北京必去的景点非这些地方莫属'
//               },
//                {
//                   id:4,
//                   imgUrl:'http://img1.qunarzz.com/sight/source/1505/9e/21df651e19af5d.jpg_r_640x214_3ea5bb38.jpg',
//                   title:'寻找北京的皇城范儿',
//                   des:'数百年的宫廷庙宇，至今依旧威严霸气'
//               },
//                {
//                   id:5,
//                   imgUrl:'http://img1.qunarzz.com/sight/source/1505/ce/bc89bc2f0e33ea.jpg_r_640x214_3e408453.jpg',
//                   title:'学生最爱的博物馆',
//                   des:'周末干嘛？北京很多博物馆已经免费开放啦'
//               }
//           ]
//       }
//   }
}
</script>

<style lang="stylus" scoped>
    .weekend
        cursor pointer
        .weekend-header
            height .8rem
            line-height .8rem
            font-size .28rem
            text-indent .3rem
            background #eeeeff
        .weekend-content
            margin-bottom .3rem
            .weekend-img
                width 100%
            .weekend-title
                overflow: hidden
                padding-right: 1.4rem
                color: #212121
                font-size: .28rem;
                line-height: .48rem
                white-space: nowrap
                text-overflow: ellipsis
                text-indent .2rem
            .weekend-des                        
                overflow: hidden
                padding-right: 1.4rem
                color: #616161
                font-size: .24rem
                line-height: .42rem
                white-space: nowrap
                text-indent .2rem
                text-overflow: ellipsis
                
</style>
