<template>
  <div id="app">
    <router-view />
    <Nav></Nav>
  </div>
</template>
<script>
  import Nav from "@/components/nav";
  export default {
    components: { Nav },
  };
</script>
<style lang="less">
  #app {
    min-height: 100%;
    width: 100%;
    background: #ffffff !important;
    padding-bottom: 50px;
  }
</style>
