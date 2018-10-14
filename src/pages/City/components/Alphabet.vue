<template>
    <ul class="list">
        <li class="item" v-for="item of letters" 
        :key="item"
        :ref="item"
        @click="handleLetterClick"
        @touchstart="handleTouchStart"
        @touchmove="handleTouchMove"
        @touchend="handleTouchEnd"
        >{{item}}</li>
       
    </ul>
</template>

<script>
export default {
    name:"CityAlphabet",
    props:{
        cities:Object
    },
    computed:{
        letters () {
            const letters =[]
            for(let i in this.cities){
                letters.push(i)
            }
            return letters
        }
    },
    data () {
        return {
            touchStatus : false,
            startY:0

        }
    },
    updated () {
        this.statrY = this.$refs['A'][0].offsetTop
    },
    methods:{
        handleLetterClick(e){
            this.$emit('change',e.target.innerText)
        },
        handleTouchStart(){
            this.touchStatus = true
        }, 
         handleTouchMove(e){
             if(this.touchStatus){          
                requestAnimationFrame(() => {
                        const startY = this.startY
                        const touchY = e.touches[0].clientY - 79
                        const index  = Math.floor((touchY-startY)/20)
                        if(index>=0 && index<=25){           
                        this.$emit('change',this.letters[index])
                    }
                })       
             }
        }, 
         handleTouchEnd(){
             this.touchStatus=false
        },
    }
}
</script>

<style scoped lang="stylus">
@import "../../../assets/styles/varibles.styl"
    .list
        position absolute 
        display flex
        justify-content center
        flex-direction column
        top 1.58rem
        right 0
        bottom 0
        width .4rem
        .item
            text-align center
            line-height .4rem
            color $bgColor
</style>
