<template>
    <div class="detail-swiper">
        <swiper class="swiperr">
            <swiper-item v-for="item in topImages" :key="item">
                <img :src="item" >
            </swiper-item>
        </swiper>
    </div>
</template>

<script>
    import Swiper from "../../../components/common/swiper/Swiper";
    import SwiperItem from "../../../components/common/swiper/SwiperItem";
    export default {
        name: "DetailSwiper",
        components:{
            Swiper,
            SwiperItem
        },
        props:{
            topImages:{
                type: Array,
                default(){
                    return []
                }
            }
        }
    }
</script>

<style scoped>
    .swiperr{
        height: 300px;
        overflow: hidden;

    }
</style>