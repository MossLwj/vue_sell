<template>
  <div id="app">
    <V-header></V-header>
    <div class="tab">
      I am tab.
    </div>
    <div class="content">
      I am content.
    </div>
    <!--<router-view/>-->
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

<style>

</style>
