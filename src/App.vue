<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style lang='scss'>
@import './css/reset.scss';
#app {
  font-family: 'Open Sans', arial, sans-serif;
}
.container {
  width: 1068px;
  margin: 0 auto;
}
@font-face {
  font-family: 'iconfont';  /* project id 637701 */
  src: url('//at.alicdn.com/t/font_637701_96ywxwrq8fy4aemi.eot');
  src: url('//at.alicdn.com/t/font_637701_96ywxwrq8fy4aemi.eot?#iefix') format('embedded-opentype'),
  url('//at.alicdn.com/t/font_637701_96ywxwrq8fy4aemi.woff') format('woff'),
  url('//at.alicdn.com/t/font_637701_96ywxwrq8fy4aemi.ttf') format('truetype'),
  url('//at.alicdn.com/t/font_637701_96ywxwrq8fy4aemi.svg#iconfont') format('svg');
}
</style>
