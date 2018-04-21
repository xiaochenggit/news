<template>
  <div class="nav-ad">
    <div class="container">
      <div class="ad-box">
        <advertising
          cname='nav-ad-logo'
          :img="{
            src: require('../../assets/logo.png'),
            alt: 'logo'
          }"
        >
        </advertising>
        <advertising
          cname='nav-ad-advertising'
          :img="{
            src: require('../../assets/nav-ad.jpg'),
            alt: '广告'
          }"
        >
        </advertising>
      </div>
    </div>
  </div>
</template>

<script>
import advertising from '../../common/advertising'
export default {
  components: {
    advertising
  }
}
</script>

<style scoped lang='scss'>
@import '../../css/common.scss';
.nav-ad {
  .container {
    .ad-box {
      margin: 25px 0 20px;
      @include flex(row);
      .nav-ad-logo {
        padding: 0 34px;
      }
    }
  }
}
</style>
