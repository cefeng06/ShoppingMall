<template>
    <div class="wrapper">
        <ul class="content">
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
            <li>{sss}</li>
        </ul>
    </div>
</template>

<script>
    import BScroll from "better-scroll"

    export default {
        name:"Category",
        data(){
            return {
                scroll:null
            }
        },
        mounted(){
            this.scroll=new BScroll(document.querySelector(".wrapper"),{
                probeType:3,
                pullUpLoad:true
            })
            console.log(this.scroll);
            this.scroll.on("scroll",() => {
            })
            this.scroll.on("pullingUp",()=>{
                console.log("上拉");
                this.scroll.finishPullUp()
            })
        }
    }
</script>

<style scoped>
    .wrapper{
        position: absolute;
        height: 150px;
        top:0;
        left: 0;
        right: 0;
        overflow: hidden;
    }
    .content{
        background-color: aliceblue;
    }
</style>