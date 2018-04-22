<template>
  <div class="home">
    <nav-top></nav-top>
    <nav-ad></nav-ad>
    <nav-tab-search/>
    <popular/>
  </div>
</template>

<script>
import NavTop from './nav-top'
import NavAd from './nav-ad'
import NavTabSearch from './nav-tab-search'
import Popular from './popular'
export default {
  components: {
    NavTop,
    NavAd,
    NavTabSearch,
    Popular
  }
}
</script>
