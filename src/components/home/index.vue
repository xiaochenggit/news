<template>
  <div class="home">
    <nav-top></nav-top>
    <nav-ad></nav-ad>
    <nav-tab-search/>
    <popular/>
    <div class="main">
      <div class="container">
        <div class="left">
          <Recommend/>
        </div>
        <div class="right">
          广告区
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import NavTop from './nav-top'
import NavAd from './nav-ad'
import NavTabSearch from './nav-tab-search'
import Popular from './popular'
import Recommend from './recommend'
export default {
  components: {
    NavTop,
    NavAd,
    NavTabSearch,
    Popular,
    Recommend
  }
}
</script>
<style lang="scss" scoped>
@import '../../css/common.scss';
.main {
  margin-top: 30px;
  .container {
    @include flex(row);
    .left {
      width: 696px;
    }
    .right {
      width: 324px;
      margin-left: 48px;
    }
  }
}
</style>
