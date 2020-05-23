<template>
  <tab-bar>
    <tab-bar-iten path="/home" activeColor="pink">
      <img slot="item-icon" src="../../../assets/img/icon-earth.png" >
      <img slot="item-icon-active" src="../../../assets/img/icon-setup.png">
      <div slot="item-text">首页</div>
    </tab-bar-iten>
    <tab-bar-iten path="/category" activeColor="pink">
      <img slot="item-icon" src="../../../assets/img/icon-voice.png">
      <img slot="item-icon-active" src="../../../assets/img/icon-personal.png">
      <div slot="item-text">分类</div>
    </tab-bar-iten>
    <tab-bar-iten path="/cart" activeColor="pink">
      <img slot="item-icon" src="../../../assets/img/icon-copy.png">
      <img slot="item-icon-active" src="../../../assets/img/icon-putitaway.png">
      <div slot="item-text">购物车</div>
    </tab-bar-iten>
    <tab-bar-iten path="/profile" activeColor="pink">
      <img slot="item-icon" src="../../../assets/img/icon-introduction.png">
      <img slot="item-icon-active" src="../../../assets/img/icon-more.png">
      <div slot="item-text">我的</div>
    </tab-bar-iten>
  </tab-bar>
</template>

<script>
    import TabBar from "../../common/tabbar/TabBar"
    import TabBarIten from "../../common/tabbar/TabBarIten"

    export default {
        name: "MainTabBar",
        components:{
            TabBar,
            TabBarIten
        }
    }
</script>

<style scoped>

</style>
