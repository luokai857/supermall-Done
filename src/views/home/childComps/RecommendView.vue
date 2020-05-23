<template>
    <div class="recommend">
        <div v-for="item in recommends" class="recommend-item" :key="item.image">
            <a :href="item.link">
                <img :src="item.image">
                <div>{{item.title}}</div>
            </a>
        </div>
    </div>
</template>

<script>
    export default {
        name: "RecommendView",
        props:{
            recommends:{
                type:Array,
                default() {
                    return []
                }
            }
        }
    }
</script>

<style scoped>
    .recommend{
        display: flex;
        flex-flow: row nowrap;
        margin: 1rem 0;
        text-align: center;
        padding: 10px 0 20px;
        border-bottom: 10px solid #eee;
    }
    .recommend a{
        flex: 1;
        text-align: center;
    }
    .recommend img{
        width: 80%;
        margin: 0 auto;
        margin-bottom: 5px;
    }

</style>