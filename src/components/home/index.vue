<template>
  <div class="home">
    <nav-top></nav-top>
    <nav-ad></nav-ad>
    <nav-tab-search/>
  </div>
</template>

<script>
import NavTop from './nav-top'
import NavAd from './nav-ad'
import NavTabSearch from './nav-tab-search'
export default {
  components: {
    NavTop,
    NavAd,
    NavTabSearch
  }
}
</script>
