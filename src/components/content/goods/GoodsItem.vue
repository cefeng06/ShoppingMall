<template>
  <div class="goods-item">
    <img :src="goodsitem.show.img" alt="">
    <div class="goods-info">
      <p class="goods-title">{{goodsitem.title}}</p>
      <span class="goods-price">{{goodsitem.price}}</span>
      <span class="favorite">{{goodsitem.cfav}}</span>
    </div>
  </div>
</template>

<script>
export default {
  name:"GoodsItem",
  props:{
    goodsitem:{
      type:Object,
      default(){
        return []
      }
    }
  }
}
</script>

<style scoped>
  .goods-item{
    position: relative;
    padding-bottom: 40px;
    width: 48%;
  }
  .goods-item img{
    width: 100%;
    border-radius: 5px;
  }  
  .goods-info{
    position:absolute;
    bottom: 5px;
    left: 0;
    right: 0;
    font-size: 14px;
    overflow: hidden;
    text-align: center;
  }
  .goods-title{
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    margin-bottom: 3px;
  }
  .goods-price{
    color: var(--color-high-text);
    margin-right: 20px;
  }
  .goods-info .favorite {
    position: relative;
  }

  .goods-info .favorite::before {
    content: '';
    position: absolute;
    left: -15px;
    top: -1px;
    width: 14px;
    height: 14px;
    background: url("../../../assets/img/common/collect.svg") 0 0/14px 14px;
  }

</style>