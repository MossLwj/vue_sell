<template>
  <div>
    <V-header></V-header>
    <div class="tab">
      <div class="tab-item">
        <!--router-link取代了v-link-->
        <router-link :to="{ path:'/goods'}">商品</router-link>
      </div>
      <div class="tab-item">
        <router-link :to="{ path:'/ratings'}">评论</router-link>
      </div>
      <div class="tab-item">
        <router-link :to="{path:'/seller'}">商家</router-link>
      </div>
    </div>
    <!--<div class="content">-->
    <!--I am content.-->
    <!--</div>-->
    <router-view/>
  </div>
</template>

<script>
  import header from './components/header/header';

  export default {
    components: {
      'V-header': header
    }
  };
</script>

<style lang="stylus" rel="stylesheet/stylus">
  .tab
    display: flex
    width: 100%
    height: 40px
    line-height: 40px
    .tab-item
      flex: 1
      text-align: center
      & > a
        display block//使得a标签撑满整个区块，不需要点击字才能跳转页面
        text-decoration none//去掉标签的下划线
</style>
