<template>
    <div id="tab-bar">
        <slot></slot>
    </div> 
</template>

<script>
export default {

}
</script>

<style scoped>
    *{
        margin: 0;
        padding: 0;
    }
    #tab-bar{
        position: fixed;
        bottom: 0;
        left: 0;
        right: 0;
        display: flex;
        background-color:#f6f6f6;
        box-shadow: 0px -2px 1px rgba(0, 0, 0, .2);
    }  
</style>