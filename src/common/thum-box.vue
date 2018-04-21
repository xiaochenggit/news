<template>
  <div class="thum-box">
    <router-link :to="href">
      <img :src="img" :alt="alt">
      <p>{{ name }}</p>
      <span>{{ title }}</span>
    </router-link>
  </div>
</template>

<script>
export default {
  /*
   * 缩率图
   * img [String] 图片地址
   * name [String] 标题
   * alt [String] 图片 alt
   * title [String] 类型
   * href [String] 跳转链接
   */
  props: {
    img: {
      type: String,
      default: require('../assets/5-218x150.jpg')
    },
    name: {
      type: String,
      default: '初始化'
    },
    alt: {
      type: String,
      default: '初始化'
    },
    title: {
      type: String,
      default: '初始化'
    },
    href: {
      type: String,
      default: '/'
    }
  }
}
</script>

<style scoped lang='scss'>
.thum-box{
  width: 196px;
  font-size: 14px;
  line-height: 28px;
  position: relative;
  overflow: auto;
  margin-left: 22px;
  overflow: hidden;
  img{
    width: 100%;
    height: auto;
    float: left;
  }
  p{
    width: 100%;
    text-overflow: ellipsis;
    overflow: hidden;
    white-space: nowrap;
  }
  span {
    color: #fff;
    background: black;
    position: absolute;
    line-height: 20px;
    font-size: 12px;
    left: 0px;
    bottom: 28px;
    padding: 0 5px;
  }
  a {
    color: #000;
    text-decoration: none;
    &:hover {
      color: #4DB2EC;
    }
  }
}
</style>
