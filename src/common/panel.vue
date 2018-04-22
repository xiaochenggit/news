<template>
  <div :class="['panel', cname]">
    <section class="header">
      <span class="head">{{ head }}</span>
      <div class="tab" v-if="items.length">
        <transition-group name="fade">
          <router-link
            v-for="(item, index) in items"
            :key="index"
            :title="item.name"
            :to='item.href'
            v-show="showIndex === index"
          >
            {{ item.name }}
          </router-link>
        </transition-group>
        <div class="tab-btn-box" v-if="items.length > 1">
          <tab-btn @next='next' @prev='prev'/>
        </div>
      </div>
    </section>
    <section class="panel-body">
      <slot/>
    </section>
  </div>
</template>

<script>
import TabBtn from '../common/tab-btn'
export default {
  /*
  * showIndex [String] 默认显示第几条信息
  */
  data () {
    return {
      showIndex: 0
    }
  },
  /*
  * head [String] 类型
  * canme [String] className
  * items [Array] 数据 [{name: 'xxx', href = 'xxxx'}]
  * tiem [Number] 定时器间隔 默认 5000
  */
  props: {
    head: {
      type: String,
      default: '流行趋势'
    },
    cname: {
      type: String,
      default: ''
    },
    items: {
      type: Array,
      default () {
        return []
      }
    },
    time: {
      type: Number,
      default: 5000
    }
  },
  methods: {
    /** @description 翻页操作
     * 上翻页
    */
    prev () {
      this.changeShowIndex(-1)
    },
    /** @description 翻页操作
     * 下翻页
    */
    next () {
      this.changeShowIndex(1)
    },
    /** @description 翻页
     * 清理定时间 || 判断边界 || 开启定时器
     */
    changeShowIndex (num) {
      this.timer && clearInterval(this.timer)
      this.showIndex = this.showIndex + num
      if (this.showIndex < 0) {
        this.showIndex = this.items.length - 1
      }
      if (this.showIndex > this.items.length - 1) {
        this.showIndex = 0
      }
      this.createTimer()
    },
    /** @description 定时器
     * 传入 time
     */
    createTimer () {
      this.timer = setInterval(() => {
        this.changeShowIndex(1)
      }, this.time)
    }
  },
  mounted () {
    // 默认开始定时器
    this.timer || this.createTimer()
  },
  components: {
    TabBtn
  }
}
</script>

<style scoped lang='scss'>
@import '../css/common.scss';
.panel {
  .header {
    @include flex(row);
    line-height: 22px;
    padding: 24px;
    .head {
      @include btn();
      font-size: 12px;
      line-height: 25px;
      height: 25px;
      padding: 0 10px;
    }
    .tab{
      flex: 1;
      line-height: 25px;
      margin-left: 24px;
      height: 25px;
      a {
        color: #111;
        font-size: 15px;
        text-decoration: none;
        display: inline-block;
        max-width: 500px;
        @include verflowText();
        &.fade-enter-active, .fade-leave-active {
          transition: all .5s;
        }
        &.fade-enter, .fade-leave-to  {
          opacity: 0;
          transform: translateX(-24px)
        }
        &:hover {
          color: #4DB2EC;
        }
      }
      .tab-btn-box {
        float: right;
        line-height: 23px;
      }
    }
  }
}
</style>
