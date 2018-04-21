<template>
  <div class="search">
    <em class="icon-search iconfont" @click="changeBodyShow"></em>
    <transition name="fade">
      <div class="body" v-show="isBodyShow">
        <input type="text" placeholder="请输入"><button>搜索</button>
      </div>
    </transition>
  </div>
</template>

<script>
export default {
  data () {
    return {
      isBodyShow: false
    }
  },
  methods: {
    changeBodyShow () {
      this.isBodyShow = !this.isBodyShow
    }
  }
}
</script>

<style scoped lang='scss'>
@import '../css/common.scss';
.search {
  width: 100%;
  height: 100%;
  position: relative;
  .iconfont {
    font-size: 24px;
    position: absolute;
    right: 20px;
    top: 50%;
    transform: translateY(-50%);
    cursor: pointer;
  }
  .body {
    &.fade-enter-active, .fade-leave-active {
      transition: all .5s;
    }
    &.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
      opacity: 0;
      transform: translateY(20px)
    }
    line-height: 30px;
    padding: 20px;
    border-top: 2px solid #4DB2EC;
    box-shadow: 0px 4px 12px #d3c9c9;
    background-color: #fff;
    position: absolute;
    top: 100%;
    left: 0;
    right: 0;
    &::before {
      content: '';
      border-left: 5px solid transparent;
      border-right: 5px solid transparent;
      border-bottom: 5px solid #4DB2EC;
      position: absolute;
      top: -7px;
      right: 25px;
    }
    @include flex(row);
    input {
      outline: none;
      height: 30px;
      border: 1px solid #eaeaea;
      color: #444;
      text-indent: 10px;
      flex: 1;
    }
    button {
      @include btn();
      transition: background-color 0.5s;
    }
    button:hover {
      background-color: #4DB2EC;
    }
  }
}
</style>
