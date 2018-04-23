<template>
  <div class="tab-switch">
    <section class="top" :style="{'border-bottom-color': color}">
      <em class="label" :style="{'background-color': color}">{{ label }}</em>
      <ul class="nav">
        <li v-for="(item, index) in items"
          :key="index"
          :style="{'color': showIndex === index ? color: ''}"
          @mouseover="addColor($event, showIndex === index)"
          @mouseout="removeColor($event, showIndex === index)"
          @click="changeShowIndex(index)"
        >
          {{item.label}}
        </li>
      </ul>
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
        return [{
          label: '所有',
          articles: [{
            name: '完美旅行的正确打开方式 所有',
            time: '2018-1-1',
            num: 0
          }]
        }, {
          label: '健康养生',
          articles: [{
            name: '完美旅行的正确打开方式 健康养生',
            time: '2018-1-1',
            num: 0
          }]
        }, {
          label: '商业',
          articles: [{
            name: '完美旅行的正确打开方式 商业',
            time: '2018-1-1',
            num: 0
          }]
        }, {
          label: '时尚2018',
          articles: [{
            name: '完美旅行的正确打开方式 时尚2018',
            time: '2018-1-1',
            num: 0
          }]
        }, {
          label: '学习探索',
          articles: [{
            name: '完美旅行的正确打开方式 学习探索',
            time: '2018-1-1',
            num: 0
          }]
        }, {
          label: '推荐',
          articles: [{
            name: '完美旅行的正确打开方式 推荐',
            time: '2018-1-1',
            num: 0
          }]
        }, {
          label: '旅行',
          articles: [{
            name: '完美旅行的正确打开方式 旅行',
            time: '2018-1-1',
            num: 0
          }]
        }, {
          label: '时尚',
          articles: [{
            name: '完美旅行的正确打开方式 时尚',
            time: '2018-1-1',
            num: 0
          }]
        }]
      }
    }
  },
  data () {
    /** @description
     * showIndex 当前显示的下标
     */
    return {
      showIndex: 0
    }
  },
  methods: {
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
    line-height: 28px;
    height: 28px;
    border-bottom: 2px;
    border-bottom-style: solid;
    font-size: 14px;
    .label {
      float: left;
      padding: 0 10px;
      color: #fff;
      margin-right: 30px;
    }
    .nav{
      display: inline-block;
      li {
        float: left;
        padding: 0 15px;
        cursor: pointer;
      }
    }
  }
}
</style>
