<template>
  <div class="goodslist">
    <goods-item v-for="items in goods" :goodsitem="items" :key="items.id"/>
  </div>
</template>

<script>
  import GoodsItem from "./GoodsItem"
  export default {
    name:"GoodsList",
    components:{
      GoodsItem
    },
    props:{
      goods:{
        type:Array,
        default(){
          return []
        }
      }
    }
  }

</script>

<style scoped>
  .goodslist{
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
  }

</style>