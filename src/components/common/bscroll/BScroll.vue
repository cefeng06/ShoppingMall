<template>
  <div class="wrapper" ref="">
    <div class="content">
      <slot></slot>
    </div>
  </div>
  
</template>

<script>
import BScroll from "better-scroll"
export default {
  name:"BScroll",
  data(){
    return {
      scroll:null
    }
  },
  mounted(){
    this.scroll=new BScroll(this.$refs.wrapper)
    
  }
}
</script>