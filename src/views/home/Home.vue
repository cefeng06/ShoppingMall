<template>
    <div id="home">
        <nav-bar class="home-nav"><div slot="center">购物街</div></nav-bar>
        <div class="wrapper">
            <div class="content">
                <swiper-1 :banner="banner"/>
                <home-recommend :recommend="recommend"/>        
                <home-feature/>
                <tab-control :titles='["流行","新款","精选"]' class="tab-control" @tabClick="tabclick"/>
                <goods-list :goods="showGoods"/>
            </div>
        </div>



    </div>
</template>

<script>
    import NavBar from "../../components/common/navbar/NavBar"
    import Swiper1 from '../../components/common/swiper/Swiper1.vue'
    import HomeRecommend from './childCompos/HomeRecommend.vue'
    import HomeFeature from './childCompos/HomeFeature.vue'
    import TabControl from '../../components/content/tabControl/TabControl.vue'
    import GoodsList from '../../components/content/goods/GoodsList'
    
    import {getHomeMutidata,getHomeGoods} from "../../network/home"

    // import BScroll from "../../components/common/bscroll/BScroll"

    export default {
        name:"Home",
        components: {
            NavBar,
            Swiper1,
            HomeRecommend,
            HomeFeature,
            TabControl,
            GoodsList,
            // BScroll
        },
        data(){
            return{
                banner:[],
                recommend:[],
                goods:{
                    "pop":{
                        page:0,
                        goodsList:[]
                    },
                    "new":{
                        page:0,
                        goodsList:[]
                    },
                    "sell":{
                        page:0,
                        goodsList:[]
                    },                                        
                },
                currentTab:"pop"
            }
        },
        created(){
            //请求首页数据
            this.getHomeMutidata()
            //请求商品
            this.getHomeGoods("pop")
            this.getHomeGoods("new")
            this.getHomeGoods("sell")
        },
        computed:{
            showGoods(){
                return this.goods[this.currentTab].goodsList
            }
        },
        methods:{
            tabclick(index){
                switch(index){
                    case 0:
                        this.currentTab="pop";
                        break;
                    case 1:
                        this.currentTab="new";
                        break;          
                    case 2:
                        this.currentTab="sell";
                        break;                                        
                }
            },
            getHomeMutidata(){
                getHomeMutidata().then(res =>{
                    console.log(res);
                    this.banner=res.data.banner.list;
                    this.recommend=res.data.recommend.list;
                })                
            },
            getHomeGoods(type){
                const page=this.goods[type].page+1;
                getHomeGoods(type,page).then(res => {
                    this.goods[type].goodsList.push(...res.data.list);
                    this.goods[type].page+=1;
                })                
            }
        }
    }
</script>

<style scoped>
    #home{
        padding-top: 44px;
    }
    .home-nav{
        position: fixed;
        left: 0;
        right: 0;
        top: 0;
        z-index: 9;
        background-color: var(--color-tint);
        color: white;
    }
    .tab-control{
        position: sticky;
        top: 44px;
        z-index: 9;
    }
</style>