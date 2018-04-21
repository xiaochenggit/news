<template>
  <div class="nav-tab-search">
    <div class="container">
      <nav-tab :items="navTabArray"/>
      <div class="search-box">
        <search/>
      </div>
    </div>
  </div>
</template>

<script>
import NavTab from '../../common/nav-tab.vue'
import Search from '../../common/search.vue'
export default {
  data () {
    return {
      navTabArray: [{
        name: '新闻',
        array: [{
          name: '把知识化为能力，只要这三个步骤',
          img: require('../../assets/5-218x150.jpg'),
          href: '/'
        }, {
          name: '把知识化为能力，只要这三个步骤',
          img: require('../../assets/5-218x150.jpg'),
          href: '/'
        }, {
          name: '把知识化为能力，只要这三个步骤',
          img: require('../../assets/5-218x150.jpg'),
          href: '/'
        }, {
          name: '把知识化为能力，只要这三个步骤',
          img: require('../../assets/5-218x150.jpg'),
          href: '/'
        }, {
          name: '把知识化为能力，只要这三个步骤',
          img: require('../../assets/5-218x150.jpg'),
          href: '/'
        }]
      }, {
        name: '时尚',
        array: [{
          name: '把知识化为能力，只要这三个步骤',
          img: require('../../assets/5-218x150.jpg'),
          href: '/'
        }]
      }, {
        name: '小技巧',
        array: [{
          name: '把知识化为能力，只要这三个步骤',
          img: require('../../assets/5-218x150.jpg'),
          href: '/'
        }]
      }, {
        name: '生活方式',
        array: [{
          name: '把知识化为能力，只要这三个步骤',
          img: require('../../assets/5-218x150.jpg'),
          href: '/'
        }]
      }, {
        name: '视频',
        array: [{
          name: '把知识化为能力，只要这三个步骤',
          img: require('../../assets/5-218x150.jpg'),
          href: '/'
        }]
      }]
    }
  },
  components: {
    NavTab,
    Search
  }
}
</script>

<style scoped lang='scss'>
.nav-tab-search {
  height: 52px;
  box-shadow: 0px 4px 8px #d3c9c9;
  .container {
    position: relative;
  }
  .search-box {
    width: 345px;
    height: 52px;
    position: absolute;
    top: 0;
    right: 0;
  }
}
</style>
