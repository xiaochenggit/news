<template>
  <div class="tab-switch">
    <section class="top" :style="{'border-bottom-color': color}">
      <em class="label" :style="{'background-color': color}">{{ label }}</em>
      <ul class="nav prev">
        <li v-for="(item, index) in prevItems"
          :key="index"
          :style="{'color': showIndex === index ? color: ''}"
          @mouseover="addColor($event, showIndex === index)"
          @mouseout="removeColor($event, showIndex === index)"
          @click="changeShowIndex(index)"
        >
          {{item.label}}
        </li>
      </ul>
      <em
       class="label more"
       @mouseover="mouseOverMore()"
       @mouseout="mouseOutMore()"
       v-if="nextItems.length"
       ref="more"
      >
        更多
        <span class="iconfont icon-xia"></span>
      </em>
      <transition name='fade'>
        <ul class="nav next" v-show="isShowNext"
          @mouseover="mouseOverMore()"
          @mouseout="mouseOutMore()"
        >
          <li v-for="(item, index) in nextItems"
            :key="index"
            :style="{'color': showIndex === (index + num) ? color: ''}"
            @mouseover="addColor($event, showIndex === (index + num))"
            @mouseout="removeColor($event, showIndex === (index + num))"
            @click="changeShowIndex(index + num)"
          >
            {{item.label}}
          </li>
        </ul>
      </transition>
    </section>
    <section class="body">
      <div v-for="(item, index) in items"
        :key="index"
        v-show="index === showIndex"
      >
        {{item.articles[0].name}}
      </div>
    </section>
  </div>
</template>
<script>
export default {
  props: {
    /* props 描述
     * label [String] 标题名字
     * color [String] 颜色
     * items [Array] 数据
     * num 分割数据的位置
     */
    label: {
      type: String,
      default: '推荐'
    },
    color: {
      type: String,
      default: 'red'
    },
    items: {
      type: Array,
      default () {
        return []
      }
    },
    num: {
      type: Number,
      default: 8
    }
  },
  data () {
    /** @description
     * showIndex 当前显示的下标
     * prevItems [array] 数据上半部分
     * nextItems [array] 数据下半部分
     * isShowNext [boolean] 是否显示更多栏
     */
    return {
      showIndex: 0,
      prevItems: [],
      nextItems: [],
      isShowNext: false
    }
  },
  watch: {
    /**
     * 监控items的变化实时更新数据
    */
    'items': function () {
      this.sliceArray()
    }
  },
  created () {
    this.sliceArray()
  },
  methods: {
    /**
     * 把数据根据分割部分分割成两段
     */
    sliceArray () {
      this.prevItems = this.items.slice(0, this.num)
      this.nextItems = this.items.slice(this.num)
    },
    /* addColor removeColor 改变颜色
    * 加一个判断，当前tab不可改变
    */
    addColor (e, flg) {
      if (flg) {
        return false
      }
      e.target.style.color = this.color
    },
    removeColor (e, flg) {
      if (flg) {
        return false
      }
      e.target.style.color = ''
    },
    /**
     * 更多 移入移出事件
    */
    mouseOverMore () {
      let style = this.$refs.more.style
      style.color = '#fff'
      style.backgroundColor = this.color
      this.isShowNext = true
    },
    mouseOutMore (e) {
      let style = this.$refs.more.style
      style.cssText = ''
      this.isShowNext = false
    },
    /** changeShowIndex
     * 改变 showIndex
     */
    changeShowIndex (index) {
      this.showIndex = index
    }
  }
}
</script>

<style scoped lang='scss'>
.tab-switch {
  .top {
    position: relative;
    color: #aaaaaa;
    line-height: 28px;
    height: 28px;
    border-bottom: 2px;
    border-bottom-style: solid;
    font-size: 14px;
    .label {
      float: left;
      padding: 0 10px;
      color: #fff;
      margin-right: 28px;
      &.more {
        padding: 0 15px;
        cursor: pointer;
        color: #aaaaaa;
        float: right;
        margin-right: 0px;
        .iconfont {
          font-size: 18px;
        }
      }
    }
    .nav{
      display: inline-block;
      li {
        float: left;
        padding: 0 13px;
        cursor: pointer;
      }
      &.next {
        &.fade-enter-active, .fade-leave-active {
          transition: opacity 0.5s;
        }
        &.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
          opacity: 0;
        }
        background-color: #fff;
        border: 1px solid #ccc;
        display: inline-block;
        line-height: 24px;
        position: absolute;
        right: 0px;
        top: 30px;
        li {
          display: block;
          float: none;
          text-align: right;
          padding: 0 18px;
        }
      }
    }
  }
}
</style>
