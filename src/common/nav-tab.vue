<template>
  <div :class="[cname, 'nav']" v-on:mouseout.stop="changeTab(-1)">
    <ul :class="['tab',derection]">
      <li v-for="(item, index) in items" :key="index" v-on:mouseover="changeTab(index)">
        {{ item.name }}
        <em class="iconfont icon-icon-arrow-bottom2"></em>
      </li>
    </ul>
    <ul :class="['tab-box','tab-box-' + derection]" >
      <transition-group name="fade">
        <li v-for="(item, index) in items" :key="index" v-if="index === showNum" v-on:mouseover="changeTab(index)">
          <thum-box v-for="(el, num) in item.array"
            :key="num"
            :name='el.name'
            :alt='el.alt'
            :title="item.name"
            :href="item.href"
          />
        </li>
      </transition-group>
    </ul>
  </div>
</template>

<script>
import ThumBox from '../common/thum-box'
export default {
  /*
   * came [String] className
   * derection [String] tab的方向 默认为 row | column
   * items [Array] 数据 格式为 [{name: 'xxxx',array:[]}]
   */
  props: {
    cname: {
      type: String,
      default: 'nav-tab'
    },
    derection: {
      type: String,
      default: 'row'
    },
    items: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      showNum: -1
    }
  },
  methods: {
    changeTab (index) {
      this.showNum = index
    }
  },
  components: {
    ThumBox
  }
}
</script>

<style scoped lang='scss'>
@import '../css/common.scss';
.nav {
  .tab.row {
    >li{
      cursor: pointer;
      display: inline-block;
      font-size: 14px;
      font-weight: 700;
      line-height: 48px;
      padding: 0 10px;
      border-bottom: 3px solid #fff;
      position: relative;
      :after{
        content: '';
        width: 50%;
        position: absolute;
        height: 3px;
        background-color: #4DB2EC;
        bottom: 0px;
        left: 50%;
        transform: translateX(-50%);
        transition: linear 0.2s all;
        opacity: 0;
      }
      &:hover :after {
        width: 100%;
        left: 0%;
        transform: translateX(-0%);
        -moz-transform: translateX(-0%);
        -o-transform: translateX(-0%);
        -webkit-transform: translateX(-0%);
        -ms-transform: translateX(-0%);
        opacity: 1;
      }
      em{
        font-size: 12px;
      }
    }
  }
  .tab-box {
    margin-left: -22px;
    width: 1112px;
    position: relative;
    z-index: 99;
    background-color: #fff;
    li {
      padding: 22px 0;
      @include flex(row);
      &.fade-enter-active, .fade-leave-active {
        transition: all .5s;
      }
      &:nth-child(2n).fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
        opacity: 0;
        transform: translateX(22px)
      }
      &:nth-child(2n + 1).fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
        opacity: 0;
        transform: translateY(-22px)
      }
    }
    box-shadow: 0px 4px 12px #d3c9c9;
  }
}
</style>
