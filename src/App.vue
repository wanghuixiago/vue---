<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <!-- 当前路由地址所对应的内容 helloWord这个组件-->
    <keep-alive exclude="Detail">
      <router-view/>
    </keep-alive>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>

</style>
