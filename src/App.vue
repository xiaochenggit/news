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
body{
  padding-bottom: 100px;
}
#app {
  font-family: 'Open Sans', arial, sans-serif;
}
.container {
  width: 1068px;
  margin: 0 auto;
}
@font-face {
  font-family: 'iconfont';  /* project id 637701 */
  src: url('//at.alicdn.com/t/font_637701_nhau0d5844klz0k9.eot');
  src: url('//at.alicdn.com/t/font_637701_nhau0d5844klz0k9.eot?#iefix') format('embedded-opentype'),
  url('//at.alicdn.com/t/font_637701_nhau0d5844klz0k9.woff') format('woff'),
  url('//at.alicdn.com/t/font_637701_nhau0d5844klz0k9.ttf') format('truetype'),
  url('//at.alicdn.com/t/font_637701_nhau0d5844klz0k9.svg#iconfont') format('svg');
}
</style>
