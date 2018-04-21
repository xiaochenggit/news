<template>
  <div class="outher-login">
    <ul>
      <li class="icon-weibo iconfont" title="微博">
      </li>
      <li class="icon-weixin iconfont" title="微信">
      </li>
      <li class="icon-qq iconfont" title="QQ"></li>
    </ul>
  </div>
</template>

<script>
export default {
}
</script>

<style scoped lang='scss'>
.outher-login {
  display: inline-block;
  float: right;
  ul {
    display: inline-block;
    li{
      cursor: pointer;
      display: inline-block;
      margin: 0 5px;
    }
    li:hover {
      color: #4db2ec;
    }
  }
}
</style>
