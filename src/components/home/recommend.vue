<template>
  <div class="recommend">
    <TabSwitch label='推荐' color='#dd3333' :items='items'/>
  </div>
</template>

<script>
import TabSwitch from '../../common/tab-switch'
export default {
  data () {
    return {
      items: [{
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
      }, {
        label: '时尚杂志',
        articles: [{
          name: '完美旅行的正确打开方式 时尚杂志',
          time: '2018-1-1',
          num: 0
        }]
      }, {
        label: '时尚猎手',
        articles: [{
          name: '完美旅行的正确打开方式 时尚猎手',
          time: '2018-1-1',
          num: 0
        }]
      }, {
        label: '生活方式',
        articles: [{
          name: '完美旅行的正确打开方式 生活方式',
          time: '2018-1-1',
          num: 0
        }]
      }, {
        label: '街头时尚',
        articles: [{
          name: '完美旅行的正确打开方式 街头时尚',
          time: '2018-1-1',
          num: 0
        }]
      }, {
        label: '视频',
        articles: [{
          name: '完美旅行的正确打开方式 视频',
          time: '2018-1-1',
          num: 0
        }]
      }, {
        label: '饮食',
        articles: [{
          name: '完美旅行的正确打开方式 饮食',
          time: '2018-1-1',
          num: 0
        }]
      }]
    }
  },
  components: {
    TabSwitch
  }
}
</script>

<style scoped lang='scss'>

</style>
