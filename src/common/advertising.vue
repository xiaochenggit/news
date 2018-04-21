<template>
  <div
    :class="['advertising', cname]"
    :style="{'width': width, 'height': height}">
    <img :src="img.src" :alt='img.alt'>
  </div>
</template>

<script>
export default {
  /* 广告组件
  * canme [String] className
  * width [String] style.width
  * height [String] style.height
  * img [Object] img.src and img.alt
  */
  props: {
    cname: {
      type: String,
      default: ''
    },
    width: {
      type: String,
      default: '100%'
    },
    height: {
      type: String,
      default: '100%'
    },
    img: {
      type: Object,
      default () {
        return {
        }
      }
    }
  }
}
</script>

<style scoped lang='scss'>
.advertising {
  img{
    float: left;
  }
}
</style>
