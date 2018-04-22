<template>
  <div class="thum-big-img" :style="{'width': width, 'height': height}">
    <router-link :to='href'>
      <img :src="img" :alt="name" :style="{'width': width, 'height': height}">
      <div class="thum-des">
        <span>{{ label }}</span>
        <h2 :class="size">{{ name }}</h2>
        <p v-if="time">{{ time }}</p>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  /** @description
   * label [String] 标签
   * name [String] 文章名字
   * img [String] 缩略图地址
   * href [String] 链接地址
   * width [Number] 宽度
   * height [Number] 高度
   * time [String] 发布时间 可有可无
   * size [String] 标题大小 md sm
  */
  props: {
    label: {
      type: String,
      default: '标签',
      required: true
    },
    name: {
      type: String,
      default: '我是标题',
      required: true
    },
    img: {
      type: String,
      default: '',
      required: true
    },
    href: {
      type: String,
      default: '/',
      required: true
    },
    width: {
      type: String,
      defaul: '0px'
    },
    height: {
      type: String,
      defaul: '0px'
    },
    time: {
      type: String,
      default: ''
    },
    size: {
      type: String,
      default: 'sm'
    }
  }
}
</script>

<style scoped lang='scss'>
@import '../css/common.scss';
.thum-big-img {
  position: relative;
  overflow: hidden;
  a{
    overflow: hidden;
  }
  img {
    transition: all 0.5s;
  }
  &:hover img {
    transform: scale(1.2);
  }
  &:hover .thum-des span {
    background-color: #4DB2EC;
  }
  .thum-des {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    padding: 0 24px;
    span {
      @include btn();
      font-size: 12px;
      line-height: 20px;
      padding: 0 5px;
    }
    h2 {
      @include overflowText();
    }
    h2.md{
      font-size: 24px;
      line-height: 40px;
      color: #fff;
    }
    h2.sm{
      font-size: 18;
      line-height: 32px;
      color: #fff;
    }
    p {
      font-size: 12px;
      color: #fff;
      line-height: 24px;
    }
  }
}
</style>
