<template>
    <div class="swiper">
        <div class="swiper-group">
            <swiper-item v-for="(item,index) in banner" :key="item.id" v-show="index === currentIndex">
                <a :href="item.link">
                    <img :src="item.image">
                </a>
            </swiper-item>            
        </div>
        <!-- 动态标记 -->
        <div class="indicator">
            <slot name="indicator" v-if="showIndicator && slideCount>1">
                <div v-for="(item, index) in slideCount" class="indi-item" :class="{active: index === currentIndex}" :key="index"></div>
            </slot>
        </div>
    </div>
    
</template>

<script>
import SwiperItem from "./SwiperItem"
export default {
    name:"Swiper",
    components:{
        SwiperItem
    },
    props:{
        banner:{
            type:Array,
            default(){
                return []
            }
        },
        loop:{
            type:Boolean,
            default:true
        },
        autoplay:{
            type:Boolean,
            default:true            
        },
        interval:{
            type:Number,
            default:1000            
        },
        animDuration:{
            type:Number,
            default:300
        },
        moveRatio:{
            type:Number,
            default:0.5
        },
        showIndicator: {
            type: Boolean,
            default: true
        },      
    },
    data(){
        return{
            slideCount:0,  //轮播元素个数
            totalWidth:0,  //swiper宽度
            swiperStyle: {}, //样式
            currentIndex: 0, //当前索引
            scrolling: false, //是否正在滚动        
        }
    },
    mounted:function(){
        this.handleDom();
        this.startTimer();
    },
    methods:{
        // *****定时器操作******
        startTimer:function(){
            this.playTimer=setInterval(() => {
                if(++this.currentIndex>this.slideCount-1){
                    this.currentIndex=0
                    console.log(this.currentIndex);
                }
            }, this.interval)
        },
        // stopTimer: function () {
        //     window.clearInterval(this.playTimer);
        // },
        // *****操作DOM******
		handleDom: function () {
            // 1.获取要操作的元素
            let swiperEl = document.querySelector('.swiper-group');
            let slidesEls = swiperEl.getElementsByClassName('slide');
            // 2.保存个数
            this.slideCount = slidesEls.length;
        }
    }

}    
</script>

<style scoped>
    .swiper{
        position: relative;
    }
    .swiper-group{
        display: flex;
        overflow: hidden;
    }
    .indicator{
        display: flex;
        justify-content: center;
        position: absolute;
        width: 100%;
        bottom: 8px;
    }
    .indi-item{
        box-sizing: border-box;
        width: 8px;
        height: 8px;
        border-radius: 4px;
        background-color: #fff;
        line-height: 8px;
        text-align: center;
        font-size: 12px;
        margin: 0 5px;
    }
    .indi-item.active {
        background-color: rgba(212,62,46,1.0);
    }
    
</style>