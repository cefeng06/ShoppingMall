<template>
    <div id="tab-bar-item">
        <div class="tab-bar-item" @click="itemClick">
            <div class="item-icon" v-show="!isActive" @><slot name="item-icon"></slot></div>
            <div class="item-icon-active" v-show="isActive"><slot name="item-icon-active"></slot></div>
            <div class="item-text" :style="activeStyle"><slot name="item-text"></slot></div>
         </div>
    </div> 
</template>

<script>
export default {
    name:"TabBarItem",
    props:{
        path:String,
        activeColor:{
            type:String,
            default:"red"
        }
    },
    computed:{
        isActive(){
            return this.$route.path.indexOf(this.path)!==-1
        },
        activeStyle(){
            return this.isActive?{color:this.activeColor}:{}
        }
    },
    methods:{
        itemClick(){
            this.$router.replace(this.path)
        }
    }
}
</script>
<style scoped>
    #tab-bar-item{
        flex: 1;
        text-align: center;
        height: 49px;
        font-size: 14px;
    }
    .tab-bar-item img{
        width: 20px;
        height: 20px;
        margin-top: 5px;
        margin-bottom: 2px;
        vertical-align: middle;
    }
</style>>