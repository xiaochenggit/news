<template>
  <div class="tab-btn">
    <span class="iconfont icon-previous" @click="prev"></span>
    <span class="iconfont icon-next" @click="next"></span>
  </div>
</template>

<script>
export default {
  /*
   * 执行父元素监控的prev, next
   */
  methods: {
    prev () {
      this.$emit('prev')
    },
    next () {
      this.$emit('next')
    }
  }
}
</script>
<style lang="scss" scoped>
.tab-btn {
  span {
    cursor: pointer;
    color: #ccc;
    display: inline-block;
    padding: 0 5px;
    border: 1px solid #ccc;
    transition: all 0.5s;
    &:hover {
      background-color: #4DB2EC;
      border-color: #4DB2EC;
      color: #fff;
    }
  }
}
</style>
