<template>
  <div class="header">
    <span>城市选择</span>
    <router-link to="/">
      <div class="iconfont back-icon">&#xeb99;</div>
    </router-link>
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~@/assets/styles/varibles.styl'
  .header
    position relative
    overflow hidden
    height .86rem
    line-height .86rem
    text-align center
    color #fff
    background $bgcolor
    font-size .32rem
    .back-icon
      position absolute
      top 0
      left 0
      width .64rem
      text-align center
      font-size .4rem
      color #fff
</style>
