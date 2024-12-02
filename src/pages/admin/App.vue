//前言，这个app.vue是一个整体的底色，就是所有页面都会以这些为底色，这个就不要动了。容易出事。如果改了的话那么记得改回正常版本
//那个版本信息的东西在这个Home里面，等大家决定好的话看看要不要改成什么
<template>
  <div id="app">
    <router-view></router-view>
  </div>
</template>

<script>
  export default {
    name: 'app',
    components: {}
  }
</script>

<style lang="less">
  body {
    margin: 0;
    padding: 0;
    font-family: "Helvetica Neue",Helvetica,"PingFang SC","Hiragino Sans GB","Microsoft YaHei","微软雅黑",Arial,sans-serif;
    font-size: 14px;
    -webkit-font-smoothing: antialiased;
    background-color: #324157;
  }

  #app {
    position: absolute;
    top: 0;
    bottom: 0;
    width: 100%;
  }
</style>
