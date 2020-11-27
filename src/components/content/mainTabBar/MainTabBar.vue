<template>
  <div id="main-tab-bar">
    <tab-bar>
      <tab-bar-item path="/home" activeColor="#993333">
        <img slot="item-icon" src="../../../assets/img/tabbar/home.svg">
        <img slot="item-icon-active" src="../../../assets/img/tabbar/home_active.svg">
        <div slot="item-text">首页</div>        
      </tab-bar-item>
      <tab-bar-item path="/category" activeColor="#993333">
        <img slot="item-icon" src="../../../assets/img/tabbar/category.svg">
        <img slot="item-icon-active" src="../../../assets/img/tabbar/category_active.svg">
        <div slot="item-text">分类</div>         
      </tab-bar-item>
      <tab-bar-item path="/shopcart" activeColor="#993333">
        <img slot="item-icon" src="../../../assets/img/tabbar/shopcart.svg">
        <img slot="item-icon-active" src="../../../assets/img/tabbar/shopcart_active.svg">      
        <div slot="item-text">购物车</div>          
      </tab-bar-item>
      <tab-bar-item path="/profile" activeColor="#993333">
        <img slot="item-icon" src="../../../assets/img/tabbar/profile.svg">
        <img slot="item-icon-active" src="../../../assets/img/tabbar/profile_active.svg">         
        <div slot="item-text">我的</div>          
      </tab-bar-item>      
    </tab-bar>    
  </div>
    
</template>

<script>
import TabBar from "../../common/tabbar/TabBar"
import TabBarItem from "../../common/tabbar/TabBarItem"

export default {
    name:"MainTabBar",
    components:{
        TabBar,
        TabBarItem
    }
}
</script> 

<style scoped>
  #main-tab-bar{
    background-color: #fff;
    position:fixed;
    bottom: 0;
    left: 0;
    right: 0;
    z-index: 10;
  }
</style>