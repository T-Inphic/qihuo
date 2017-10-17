<template>
  <div id="app">
    <header class="head">
      <div class='leftLogo'><img src="../static/images/logo.png" alt=""></div>
      <div class='rightContact'>
        <p class="call"><span class="phone"></span>咨询方式：18637118816</p>
        <p class="call"><a target="_blank" href="http://wpa.qq.com/msgrd?v=3&amp;uin=646086510&amp;site=qq&amp;menu=yes"><span class="QQ"></span>QQ：646086510</a></p>
      </div>
    </header>
    <home/>
    <footer class="foot">
      Copyright  河南开颜信息服务有限公司 All Rights Reserved. 豫ICP备17040035号
    </footer>
  </div>
</template>

<script>
import Home from './components/Home'

export default {
  name: 'app',
  components: {
    Home
  }
}
</script>

<style lang="less">
@import './less/reset.less';
@import './less/headFoot.less';
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #333;
}
</style>
