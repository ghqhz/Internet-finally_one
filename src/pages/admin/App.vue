//前言，这个app.vue是一个整体的底色，就是所有页面都会以这些为底色，这个就不要动了。容易出事。如果改了的话那么记得改回正常版本
//那个版本信息的东西在这个Home里面，等大家决定好的话看看要不要改成什么
<template>
  <div>
    <div id="app">
      <router-view></router-view>
    </div>
  </div>
</template>
//对应网址：http://localhost:8080/admin/login 不过目前的问题是这个登录界面好像也会干涉到别的地方，这个不太理解
//严格来说这个界面影响了很多东西，感觉就像一个大杂烩，看不太明白
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
    background-color:white /* 将背景色设为纯透明 */
  /* 其他样式 */
};
  
//这个颜色是登录页面的颜色，所以这个应该是负责登录页面的那个配置
  #app {
    position: absolute;
    top: 10;
    bottom: 0;
    width: 100%;
    //height:100%;
    //background-color: white;
  }//这个20％是到左边的空间
 

</style>
