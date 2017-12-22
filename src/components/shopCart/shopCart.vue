<template>
  <div class="shopCart">
    <div class="content">
      <div class="content-left">
        <div class="logo-wrapper">
          <div class="logo">
            <span class="icon-shopping_cart"></span>
          </div>
        </div>
        <div class="price"></div>
        <div class="desc"></div>
      </div>
      <div class="content-right">

      </div>
    </div>
  </div>
</template>

<script type="text/ecmascript-6">
  export default {
    // name: "shopCart"
  };
</script>

<style lang="stylus" rel="stylesheet/stylus">
  .shopCart
    position: fixed
    left: 0
    bottom: 0
    width: 100%
    z-index: 50
    height: 48px
    background: #000
</style>
