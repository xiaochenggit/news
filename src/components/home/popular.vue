<template>
  <div class="popular-box">
    <div class="container">
      <panel head='流行趋势' cname='popular' :items='items'>
      </panel>
    </div>
  </div>
</template>

<script>
import Panel from '../../common/panel'
export default {
  data () {
    return {
      items: [{
        name: '这是我非常努力的唯一理由',
        href: '/'
      }, {
        name: '聆听流行音乐 一睹帅气风彩',
        href: '/'
      }, {
        name: '学院风春季时装展示',
        href: '/'
      }, {
        name: '年轻人热衷的义工旅行 是一厢情愿还是负责任的旅行？',
        href: '/'
      }]
    }
  },
  components: {
    Panel
  }
}
</script>

<style scoped>

</style>
