<template>
  <div class="recommend">
    <div v-for="items in recommend" :key="items.id" class="recommend-item">
      <a :href="items.link">
      <img :src="items.image">
      </a>
      <div>{{items.title}}</div>
    </div>
  </div>
  
</template>

<script>
export default {
  name:"HomeReconmend",
  props:{
    recommend:{
      type:Array
    }
  }
}
</script>

<style scoped>
  .recommend{
    display: flex;
    text-align: center;
    border-bottom: 10px solid #eee;
  }
  .recommend-item{
    flex: 1;
    margin: 5px 8px;
    font-size: 12px;
  }
  .recommend-item img{
    width: 100%;
  }  
</style>