<template>
    <div id="detail">
        <detail-nav-bar class="datail-nav"/>
        <scroll class="content">
            <detail-swiper :top-images="topImages"></detail-swiper>
            <detail-bace-info :goods="goods"></detail-bace-info>
            <detail-shop-info :shop="shop"></detail-shop-info>
            <detai-goods-info :detail-info="detailInfo"></detai-goods-info>
        </scroll>

    </div>
</template>

<script>
   import DetailNavBar from "./childComps/DetailNavBar";
   import DetailSwiper from "./childComps/DetailSwiper";
   import DetailBaceInfo from "./childComps/DetailBaceInfo";
   import DetailShopInfo from "./childComps/DetailShopInfo";
   import DetaiGoodsInfo from "./childComps/DetaiGoodsInfo";

   import Scroll from "../../components/common/scroll/Scroll";

   import {getDetail,Goods,Shop} from "../../network/detail";


   export default {
        name: "Detail",
        components: {
            DetailNavBar,
            DetailSwiper,
            DetailBaceInfo,
            DetailShopInfo,
            Scroll,
            DetaiGoodsInfo
        },
        data(){
            return{
                iid:null,
                topImages:[],
                goods:{},
                shop:{},
                detailInfo:{}
            }
        },
        created() {
            //1.保存传入的iid
            this.iid = this.$route.params.iid
            //2.根据iid请求详情数据
            getDetail(this.iid).then(res =>{
                //1.获取顶部的图片轮播数据
                console.log(res);
                const data = res.result;
                this.topImages = data.itemInfo.topImages

                //2.获取商品信息
                this.goods = new Goods(data.itemInfo,data.columns,data.shopInfo.services)

                //3.创建店铺信息
                this.shop = new Shop(data.shopInfo)

                //4保存商品的详细数据
                this.detailInfo = data.detailInfo;
            })
        }
    }
</script>

<style scoped>
    #detail{
        position: relative;
        z-index: 9;
        background-color: #fff;
        height: 100vh;
    }
    .content{
        height: calc(100% - 44px);
    }
    .datail-nav{
        position: relative;
        background-color: #fff;
        z-index: 9;
    }
</style>