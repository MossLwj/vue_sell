<template>
  <div>
    <V-header :seller="seller"></V-header>

    <div class="tab border-1px">
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

<script type="text/ecmascript-6">
  import header from './components/header/header';

  const ERR_OK = 0;

  export default {
    data() {
      return {
        seller: {}
      };
    },
    created() {
      this.$http.get('/api/seller').then((response) => {
        response = response.body;
        if (response.errno === ERR_OK) {
          this.seller = response.data;
          console.log(this.seller);
        }
      });
    },
    components: {
      'V-header': header
    }
  };
</script>

<style lang="stylus" rel="stylesheet/stylus">
  @import "common/styles/mixin.styl"
  .tab
    display: flex
    width: 100%
    height: 40px
    line-height: 40px
    border-1px(rgba(7, 17, 27, 0.1))
    .tab-item
      flex: 1
      text-align: center
      & > a
        display: block //使得a标签撑满整个区块，不需要点击字才能跳转页面
        font-size: 14px
        color: rgb(77, 85, 93)
        &.active
          color: rgb(240, 20, 20)
</style>
