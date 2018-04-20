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
</style>
