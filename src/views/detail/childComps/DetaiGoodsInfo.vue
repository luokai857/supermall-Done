<template>
    <div v-if="Object.keys(detailInfo).length !==0" class="goods-info">
       <div class="info-desc clear-fix">
           <div class="start">
           </div>
           <div class="desc">{{detailInfo.desc}}</div>
           <div class="end"></div>
       </div>
        <div class="info-key">{{detailInfo.detailImage[0].key}}</div>
        <div class="info-list">
            <img v-for="(item,index) in detailInfo.detailImage[0].list" :key="index" :src="item" @load="imgLoad">
        </div>
    </div>
</template>

<script>
    export default {
        name: "DetaiGoodsInfo",
        props:{
            detailInfo:{
                type:Object
            }
        },
        data(){
            return{
                counter:0,
                imagesLeength:0
            }
        },
        methods:{
            imgLoad(){
              this.$emit('imageLoad')
            }
        },
        watch:{
            detailInfo(){
                this.imagesLeength = this.detailInfo.detailImage[0].list.length
            }
        }
    }
</script>

<style scoped>
   .goods-info{
       padding:20px 15px;
       font-size: 14px;
       border-bottom: 5px solid #f2f5f8;
   }
    .goods-info table{
        width: 100%;
        border-collapse: collapse;
    }
    .goods-info table tr{
        height: 42px;
    }
    .goods-info table tr tb{
        border-bottom: 1px solid rgba(100,100,100,.1);
    }
    .info-list img{
        width: 100%;
    }

</style>
