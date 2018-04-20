<template>
  <div class="nav-top">
    <div class="container">
      <div class="time">星期六, 四月 21, 2018</div>
      <router-link :to="{name: 'home'}">注册加入</router-link>
      <router-link :to="{name: 'home'}">我的账户</router-link>
      <router-link :to="{name: 'home'}">购物车</router-link>
      <router-link :to="{name: 'home'}">博客</router-link>
      <router-link :to="{name: 'home'}">论坛</router-link>
      <router-link :to="{name: 'home'}">联系我们</router-link>
      <router-link :to="{name: 'home'}">购买系统</router-link>
    </div>
  </div>
</template>

<script>
export default {
}
</script>
<style scoped lang='scss'>
.nav-top {
  font-size: 12px;
  line-height: 28px;
  background-color: #000;
  color: #ffffff;
  .time {
    width: 150px;
    display: inline-block;
  }
  a {
    color: #fff;
    text-decoration: none;
    margin: 0 10px;
  }
  a:hover {
    color: #4db2ec
  }
}
</style>
