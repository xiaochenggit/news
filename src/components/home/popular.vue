<template>
  <div class="popular-box">
    <div class="container">
      <panel head='流行趋势' cname='popular' :items='items'>
        <div class="popular-body">
          <div class="left">
            <thum-big-img
              width='530px'
              height='462px'
              :img='thum1.img'
              :href='thum1.href'
              :name='thum1.name'
              :label='thum1.label'
              :time='thum1.time'
              size="md"
            />
          </div>
          <div class="right">
            <thum-big-img
              width='533px'
              height='261px'
              :img='thum2.img'
              :href='thum2.href'
              :name='thum2.name'
              :label='thum2.label'
            />
            <section class="bottom">
              <thum-big-img
                width='265px'
                height='198px'
                :img='thum3.img'
                :href='thum3.href'
                :name='thum3.name'
                :label='thum3.label'
              />
              <thum-big-img
                width='265px'
                height='198px'
                :img='thum4.img'
                :href='thum4.href'
                :name='thum4.name'
                :label='thum4.label'
              />
            </section>
          </div>
        </div>
      </panel>
    </div>
  </div>
</template>

<script>
import Panel from '../../common/panel'
import ThumBigImg from '../../common/thum-big-img'
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
      }],
      thum1: {
        img: require('../../assets/1-534x462.jpg'),
        href: '/',
        name: '这是我非常努力的唯一理由',
        label: '生活方式',
        time: '2020年1月1日'
      },
      thum2: {
        img: require('../../assets/3-533x261.jpg'),
        href: '/',
        name: '聆听流行音乐 一睹帅气风彩',
        label: '旅行',
        time: '2020年1月1日'
      },
      thum3: {
        img: require('../../assets/18-265x198.jpg'),
        href: '/',
        name: '学院风春季时装展示',
        label: '时尚',
        time: '2020年1月1日'
      },
      thum4: {
        img: require('../../assets/1-265x198.jpg'),
        href: '/',
        name: '这是我非常努力的唯一理由',
        label: '生活方式',
        time: '2020年1月1日'
      }
    }
  },
  components: {
    Panel,
    ThumBigImg
  }
}
</script>

<style scoped lang='scss'>
@import '../../css/common.scss';
.popular-box {
  .popular-body {
    @include flex(row);
    .left {
      flex: 1;
      width: 532px;
      overflow: hidden;
    }
    .right {
      flex: 1;
      width: 533px;
      float: right;
      overflow: hidden;
      .bottom {
        overflow: hidden;
        @include flex(row);
        margin-top: 3px;
        justify-content: space-between;
      }
    }
  }
}
</style>
